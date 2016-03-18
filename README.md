# Slack Custom Emoji Import

Hacked this thing up to import over 500 emoji into a new Slack from another Slack.

# Setup
This crazy thing uses environment variables so that i didn't leak my
private info. You'll need three:
 - `SLACK_DOMAIN`
 - `SLACK_EMAIL`
 - `SLACK_PASSWORD`

# Run it! :dash:

Make sure you have a file called `emoji_list.txt` in along with the
script. There's one in this repo, but if you want to provide your own
you can get it from the Slack Emoji List API. The emojis that go
with the list are also here in the proper place that the script will
look for them. If for some crazy reason, you want this exact set, you
don't have to do any work! :metal:

```
$ bundle
$ SLACK_DOMAIN=foo SLACK_EMAIL=bar@example.com SLACK_PASSWORD="myf4ncyp455w0rd" bundle exec ruby ./slack_emoji_upload.rb
```

Now, go grab a :coffee: while the computer imports all the emoji! If you
have to stop it in the middle, it won't download the images again, but
it will try to import all the emoji in the list a second time.


# Caveats

This code isn't very pretty. To call it a quick hack is an understatement. :smiley:

There's no support for aliases. The code is there, but it didn't work and I haven't gone back to fix it yet. :scream:

It's slow. There's no API for emoji imports in Slack, so we're faking a
browser session with Capybara. Shhh. :no_mouth: :see_no_evil:

No tests! Wheee! :innocent:
