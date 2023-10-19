(This may no longer be required as comcast no longer appears to be injecting javascript into non-https, non-comcast/xfinity web pages on my connection

This may not be the situation for everybody, so this filter may still be of use to others)


# Privoxy Filter to Remove Comcast Injected Content
A Privoxy filter and action file pair to remove Comcast's injected javascript entirely

# Installation
You must have a working privoxy installation to use this filter.

Install the filter by dropping comcast.filter and comcast.action into privoxy's config directory.

For Windows save the files as comcast.filter.txt and comcast.action.txt

Then add these lines to privoxy's config file:

    actionsfile comcast.action
    filterfile comcast.filter

# How it works

When you set up Privoxy as an HTTP proxy, all incoming HTTP traffic will pass through it before reaching your browser.

Privoxy will scan for and remove the script that Comcast injects into your web pages before they reach you.

Then privoxy will inject a script into the page just before the `</head>` tag that executes once the page finishes loading.
Our injected script searches the page for any of comcast's injected content and removes it if found, otherwise it does nothing.

Since we already removed comcast's injected script, there should be no comcast content on the page, so the second script will only do anything if comcast changes their injected script enough to avoid the regex pattern. So it's kind of a fall-back.
