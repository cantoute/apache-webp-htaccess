
This is inspired by rules from wordpress plugin https://github.com/rosell-dk/webp-express

ADDVARY variable has a meaning and without it apache won't add the Vary header on a rewrite rule.

not sure that EXISTING variable is required, but as is it works as expected.

Having the Vary header makes this respects http current standards and makes it compatible to use behind CDN.

Note: in case CDN ignored the Vary, one could add the 'Cache-Control: Private' which explicitly bans reverse proxy caching and still take advantage of browser cache.

Hope it helps

