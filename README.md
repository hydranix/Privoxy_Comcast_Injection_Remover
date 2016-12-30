# Privoxy_Comcast_Injection_Remover
A Privoxy filter and action file pair to remove Comcast's injected javascript entirely


Install this by dropping comcast.filter ad comcast.action into privoxy's config directory.

For Windows save the files as comcast.filter.txt and comcast.action.txt


Then add this line to privoxy's config file:

filterfile comcast.filter
