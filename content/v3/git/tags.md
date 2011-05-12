---
title: Git DB Tags API v3 | developer.github.com
---

# Tags API

This tags api only deals with tag objects - so only annotated tags, not
lightweight tags.

## Get a Tag

    GET /repos/:user/:repo/tags/:sha

### Response

<%= headers 200 %>
<%= json :tag %>

## Create a Tag Object

    POST /repos/:user/:repo/tags

### Parameters

tag
: _String_ of the tag

message
: _String_ of the tag message

object
: _String_ of the SHA of the git object this is tagging

type
: _String_ of the type of the object we're tagging. Normally this is a
`commit` but it can also be a `tree` or a `blob`.

tagger.name
: _String_ of the name of the author of the tag

tagger.email
: _String_ of the email of the author of the tag

tagger.date
: _Timestamp_ of when this object was tagged

### Response

<%= headers 201,
      :Location => "https://api.github.com/repos/:user/:repo/tags/:sha" %>
<%= json :sha => "3241bfae562975622c208335e306efd9aa706687", :size => 30 %>
