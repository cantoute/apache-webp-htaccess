
This is inspired by rules used in wordpress plugin https://github.com/rosell-dk/webp-express

It will serve a webp image to browsers that can handle it.

`GET /my/image.jpg` will return image previously converted and saved as `/my/image.jpg.webp`

on debian you might want this package
```
~# apt install webp
```

imagemagick / graphicsmagic can do the job too

Hope it helps

### Notes

ADDVARY variable has a meaning and without it apache won't add the Vary header on a rewrite rule.

not sure that EXISTING variable is required, but as is it works as expected.

Having the Vary header makes this respects http current standards and makes it compatible to use behind CDN.

In case CDN ignored the Vary, one could add the 'Cache-Control: Private' which explicitly bans reverse proxy caching and still take advantage of browser cache.


