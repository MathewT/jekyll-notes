# jekyll-notes
Notes on learning Jekyll (using Docker, of course)

### Pull/install latest Jekyll Docker image

```bash
docker pull jekyll/jekyll:latest
```

### Create a new site

```bash
export site_name="my-jekyll-site" && export MSYS_NO_PATHCONV=1
docker run --rm   --volume="$PWD:/srv/jekyll"   -it jekyll/jekyll   sh -c "chown -R jekyll /usr/gem/ && jekyll new $site_name"   && cd $site_name
```

### Edit Gemfile and add webrick gem

```bash
gem 'webrick', '~> 1.3', '>= 1.3.1'
```

### Use jekyll build to build the site (from inside the new site dir)

```bash
docker run --rm   --volume="$PWD:/srv/jekyll"   -it jekyll/jekyll   jekyll build
```

### Run jekyll serve to serve local static site

```
docker run --rm   --volume="$PWD:/srv/jekyll"   -p 4000:4000 jekyll/jekyll jekyll serve
```

