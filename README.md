# MIndie Profile

Built upon [IndieWeb Example Site](https://github.com/indieweb/blank-gh-site) to give a minimally self-hosted [IndieAuth](https://indieweb.org/IndieAuth) profile. This supports metadata discovery and the deprecated `rel="authorization_endpoint"` mechanisms.

It is highly recommended to use [IndieWeb Example Site](https://github.com/indieweb/blank-gh-site) directly. However, this was made to include the missing `<link rel="indieauth-metadata" href="https://example.com/.well-known/oauth-authorization-server" />` for metadata discovery.

The following `<link>` elements reflect other MIndie projects:
1. `<link rel="indieauth-metadata" href="https://example.com/.well-known/oauth-authorization-server" />`
1. `<link rel="authorization_endpoint" href="https://example.com/selfauth/index.php" />`
1. `<link rel="token_endpoint" href="https://example.com/selfauth/token.php" />`

This provides the Profile component of [MIndie](https://github.com/carrvo/mindie).

## Setup

1. Clone to `/usr/local/src/`
1. Modify [blank-gh-site/index.html](blank-gh-site/index.html)
    1. all `<link>` elements
    1. `<title>username</title>`
    1. `I'm <span class="p-name">username</span>.`
    1. `<li><a class="u-uid u-url" href="username">My New Website</a></li>`
1. Add configuration to your Apache HTTPd configuration (example found [blank-gh-site.conf.example](blank-gh-site.conf.example)) replacing `<username>` throughout
    ```
    Alias /user/<username> /usr/local/src/mindie-profile/blank-gh-site/index.html
    <Location /user/<username>>
	    <RequireAll>
		    Require all granted
	    </RequireAll>
    </Location>
    ```

## Usage

Navigate to `https://example.com/user/<username>`

## License

Per [CC0](http://creativecommons.org/publicdomain/zero/1.0/), to the extent possible under law, [the contributors](https://github.com/indieweb/blank-gh-site/graphs/contributors) have waived all copyright and related or neighboring rights to this work.

