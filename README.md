### Redcarpet
---

https://github.com/vmg/redcarpet

```
[sudo] gem install redcarpet
[sudo] gem install redcarpet -v 2.3.0
git clone git://github.com/vmg/redcarpet.git


```

```ruby
markdown = Redcarpet::Markdown.new(renderer, extensions = {})
markdown.render("This is *bongos*, indeed.")

markdown = Redcarpet::Markdown.new(Redcarpet::Render::HTML, autolink: true, tables: true)
Redcarpet::Render::HTML.new(render_options = {})

renderer = Redcarpet::Render::HTML.new(no_links: true, hard_wrap: true)
require 'redcarpet'
require 'redcarpet/render_strip'
markdown = Redcarpet::Markdown.new(Redcarpet::Render::StripDown)
markdown.render("**This** _is_ an [example](http://example.org/).")

class CustomRender < Redcarpet::Render::HTML
  def block_quote(quote)
    %(<blockquote class="my-custom-class">#{quote}</blockquote>)
  end
end
markdown = Redcarpet::Markdown.new(CustomRender, fenced_code_blocks: true)

class ManPage < Redcarpet::Render::Base
end

class RenderWithoutCode < Redcarpet::Render::HTML
  def block_code(code, language)
    nil
  end
end

class HTMLWithPants < Redcarpet::Render::HTML
  include Redcarpet::Render::SmartyPants
end
Redcarpet::Render::SmartyPants.render("<p>Oh SmartyPants, you're so crazy...</p>")

require 'redcarpet/compat'
Markdown.new('this is my text').to_html
```

```

```
