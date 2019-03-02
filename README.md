
# Setup

Make sure something like the below is in `.bashrc`

    eval "$(rbenv init -)"
    eval "$(nodenv init -)"

Install node (for Less) and Jekyll (for local dev)

    node install
    bundle install


# Less CSS

    ./node_modules/less/bin/lessc style/less/site.less style/site.css

# Local Jekyll Dev

    bundle exec jekyll serve
