* [整合 bower 基本](http://dotwell.io/taking-advantage-of-bower-in-your-rails-4-app/)
* [整合 bower 含 Heroku Deploy 設定](http://blog.jasonkim.ca/blog/2015/06/29/setting-up-bower-on-rails-4-for-heroku/)
* [Bundle solution - rails-assets](https://rails-assets.org/)
* [Froala Editor](https://www.froala.com/wysiwyg-editor)

# 問題

* [判斷資源檔是否存在](http://j.mp/1Tj66t8)

~~~rb
def asset_available? logical_path
  if Rails.configuration.assets.compile
    Rails.application.precompiled_assets.include? logical_path
  else
    Rails.application.assets_manifest.assets[logical_path].present?
  end
end
~~~

* 在本地端開啟 `production` 環境

記得 `config/environments/production.rb` 記得把 `config.serve_static_files` 改成 `true`

~~~rb
# Disable serving static files from the `/public` folder by default since
# Apache or NGINX already handles this.
config.serve_static_files = ENV['RAILS_SERVE_STATIC_FILES'].present?
~~~
