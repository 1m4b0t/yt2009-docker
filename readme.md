# automated docker builds of yt2009
### this repo is an adaptation of [ben-pearce/cobalt-web](https://github.com/ben-pearce/cobalt-web) to make automated docker images of [ftde0/yt2009](https://github.com/ftde0/yt2009)

---

## how to use
you can just download [docker-compose.yml](https://github.com/1m4b0t/yt2009-docker/blob/main/docker-compose.yml) to an empty folder, create a folder named `data` on the same folder and then run `docker compose up -d` to have a yt2009 instance on port 8080 but you can also customize some settings for it in the environment variables, here are some examples:
- `YT2009_ENV` sets the mode of the instance, `dev` (the default) just runs it without any protection and `prod` runs it with a token system that by default generates some random tokens which you can access at the `data/config.json` file on the same folder as the docker compose file
- `YT2009_AUTO_MAINTAIN` sets the automatic cleaning of the instance, the default if you don't use this option is false but on my docker compose file i've set it to true
- `YT2009_MAINTAIN_MAX_SIZE` sets the max of the assets folder size in GB (where cached videos are stored), the default is 10
- `YT2009_MAINTAIN_MAX_CACHE_SIZE` sets the maxi cache file size in MB, the default is 15
- `YT2009_HOMEPAGETEXT` displays a banner on the homepage with whatever text you put in
- `YT2009_TOKENS` you can set custom tokens here, they have to be seperated by commas and it will get rid of the random tokens generated when first prod env

for the rest of the environment variables check [ftde0/yt2009/docker.md](https://github.com/ftde0/yt2009/blob/main/docker.md) and for other things just check the [readme.md of the original project](https://github.com/ftde0/yt2009/blob/main/readme.md)

you can also change the port that the instance runs on by changing the number to the left on this part of the docker compose file
```
    ports:
      - "8080:80"
```
