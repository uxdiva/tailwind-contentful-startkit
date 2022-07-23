
# Jekyll + Contentful + Tailwinds

This is a starter kit for using Contentful and Tailwinds with Jekyll

## Create your content model in contentful
This example uses a content model called `post`. With the fields.
- title (short-text, Entry title)
- slug (default from title)
- body (long-text, markdown)


## Add your Contentful information
_update the `_config.yml` file_
- uncomment the page_gen section and update with your contentful data source
- uncomment the contentful secont and update the word "example" with the name of your contentful space


### Run locally
- create a duplicate called `_config-secret.yml` in this file, update the "space" and "access_token" with your contentful creditials.
- add your `_config-secret.yml` to the .gitignore file
- run the server with `jekyll serve --config _config-secret.yml`

### Run on Netlify
- Add your contentful creditials into environment variables 
- put `Jekyll Contentful && Jekyll Build` in your build settings

## Example page generator
See `/_layouts/blog.html` file for a generated template example. More setting examples can be found at [Jekyll Datapage Gen](https://github.com/avillafiorita/jekyll-datapage_gen)

### Add a loop to the index page
Add a quick loop to your index page with this example using
```
{% for post in site.data.contentful.YOURSPACENAME.post %}
[{{ post.title}}](/blog/{{ post.slug }})
{% endfor %}
```


