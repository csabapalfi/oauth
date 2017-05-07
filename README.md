# local-oauth

Play around with OAuth2 APIs locally.

A bit like the [Google OAuth 2.0 Playground](https://developers.google.com/oauthplayground/) but as a node module.

## usage

### register your app
* create/register an app with your API provider of choice
* set callback URL to `http://localhost:8080`

### configure the module

* drop endpoints, client id and secret, etc in options
* you can pre-configure previously acquired auth code and tokens

### single function to call

* returns access token (and auth code, refresh token, token expiry)
* requests auth code (if not pre-configured)
    * starts local server for auth code callback
    * opens your browser with the approve URL
* requests or refreshes access token (if not pre-configured or expired)

### some examples

* [Monzo](examples/monzo.js)
* [FreeAgent](examples/freeagent.js)
* [Google](examples/google.js)
* [Facebook](examples/facebook.js) (no refresh tokens, needs manual re-auth)
* TransferWise (coming soon...)

## why?

I use it to pre-auth locally then some of my personal scheduled scripts can use the credentials (and can also refresh tokens automatically if needed).
