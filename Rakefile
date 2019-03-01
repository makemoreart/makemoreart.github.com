task :default => [:"site:build:dev"]

namespace :site do
  desc "deletes _site"
  task :delete do
    puts "deleting _site"
    system('rm -r _site')
    puts "deleting _site complete"
  end

  desc "build _site"
  namespace :build do
    desc "build and deploy dev"
    task :dev => [:"delete", :"env:dev"] do
      puts "building _site"
      system('jekyll --server')
    end

    desc "build prod"
    task :prod => [:"delete", :"env:prod"] do
      puts "building production _site"
      system('jekyll')
      puts "building _site complete"
    end

  end

  desc "change environment"
  namespace :env do
    desc "change to development environment"
    task :dev do
      puts "change to dev environment"
      updateConfig "env: dev"
    end

    desc "change to production environment"
    task :prod do
      puts "change to prod environment"
      updateConfig "env: prod"
    end
  end

end

private
  def updateConfig(rep)
    lines = IO.readlines("_config.yml");
    lines[-1] = rep
    File.open("_config.yml","w") do |file|
      lines.each do |line|
        file.write(line)
      end
    end
  end