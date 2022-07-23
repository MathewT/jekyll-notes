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

### Use jekyll build to build the site (from inside the new site dir)

```bash
docker run --rm   --volume="$PWD:/srv/jekyll"   -it jekyll/jekyll   jekyll build
```

