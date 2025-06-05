+++
title = "A Conversation on Claude Code"
date = 2025-06-05

[taxonomies]
tags=["llms", "anthropic", "claude", "vibe-coding", "ai"]
categories=["blog"] 
+++

Probably a bit late to the conversation on this one as I'm currently between jobs and so
I don't have 40 minute gaps whilst tests run to read Hacker News, but Anthropic have
just released a video discussing [Claude
Code](https://www.youtube.com/watch?v=Yf_1w00qIKc).

Honestly this is a cool piece of tooling and this is the direction that I'd like to see
LLM/AI stuff continue to move. Having something that keeps out of your way until you
want it is great, as opposed to things like Microsoft forcing Copilot down every GitHub
user's throat. A CLI tool that I can use only when I want it is great! It also sets the
incentive up to build something that's actually useful. If Claude Code isn't useful I
just wont use it and it won't get in my way. In other words, I am glad that we have
moved away from autocompletes.

I haven't had the chance to give Claude Code a proper once over, but already I can see a
few issues.

## Cost

In the video, Boris is saying that you can probably get away with 5$ for the weekend,
but if you want to use Claude Code routinely then you're looking at at least 50-100$ per
month. 100$/month is enough money that it's inacessible to most people and I think this
is probably going to exacerbate issues that we're already having with inequality.

## Security 

Maybe I just have anxiety, but letting Claude run wild on my personal machine seems
crazy. Does it do any kind of sandboxing or anything like that? It's unclear to me, but
at face value it doesn't seem like there's anything stopping Claude from hitting me with
an `rm -rf /`. I don't think it's going to exfiltrate my secrets anywhere, but I just
don't trust it not to do silly things to my system that it ought not to. In fairness,
seems like they have [quite granular
controls](https://docs.anthropic.com/en/docs/claude-code/security) over what Claude can
be allowed to do in your system, so maybe I *do* have anxiety.

## Remote only

Of course I wouldn't necessarily expect this out the gate from Anthropic as they stand
to make money off Claude Code, but I struggle to be super happy about tools whose only
backend is a paid service with no option of moving over to self hosting something. It's
not that I disagree with Anthropic's model, it's just a shame to build what looks like
such a good UI and give it only a proprietary backend. I'm sure it's only a matter of
time before there's a really good open source alternative anyway.
