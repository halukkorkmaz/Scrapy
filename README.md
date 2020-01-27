# Scrapy

## To start the shell
`scrapy shell "http://quotes.toscrape.com/page/1/"`

## Some queries with response

1. `content = response.css(“div.quote”)`
Content has a list that hold all divs named quote.

2. `first_quote_div = content[0]`
Very first quote div in content list.

3. `title = first_quote_div.css(“span.text::text”).extract_first()`
title —> “The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”

4. `author = first_quote_div.css(“small.author::text”).extract_first()`
author —> “Albert Einstein”

5. `for quote in content:`
   `...:     text = quote.css("span.text::text").extract_first()` 
   `...:     author = quote.css("small.author::text").extract_first()`
   `...:     tags = quote.css("div.tags a.tag::text").extract()`
   `...:     print(dict(text=text, author=author, tags=tags))`
    


