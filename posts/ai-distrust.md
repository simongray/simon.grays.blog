---
date: 2026-11-01
location: Ørestad, Copenhagen
tags: llm, ai, bouldering
---

# The distrust is natural

Lately, I have been thinking about how people respond psychologically to LLM use. The honeymoon phase is over, and generative AI now affects nearly every part of society. The speed of this change is revolutionary, almost in the literal sense.

And society is reacting. More and more people are integrating AI into their personal workflows, but negative reactions to AI use are growing alongside it.

I have come to realise that the distrust is _natural_ because the effort is **unnatural**. I have used LLMs heavily in my own software development over the past year, yet I feel the same distrust towards most things made with them.

At first, I thought it was collateral damage from the onslaught of [vibe-coded][vibe] projects by novices and non-developers. You recognise one instantly:

> "Hi everyone! 👋 I made an app for [XYZ]."
 
followed by a long announcement written in emoji-laden Markdown. The app itself will have a half-baked and unmistakably LLM-generated UI, often paired with impressive and mostly superficial 3D rendering.

My intuition was that the sheer number of vibe-coded projects had simply worn us out, and that this fatigue now pollutes our attitude towards all LLM use.

Later I realised that it actually makes **no difference** whether I know a skilled developer is behind a project or not. Even the most skilled developers can't match the implementation speed of several agents working in parallel. Working at that speed takes an unnatural, superhuman effort, so _of course_ we can't help but feel uneasy when we come across projects built that way.

So mentioning LLM use invites a negative reaction, and merely suspecting it (which people increasingly do) invites a [purity test][purity-test]. In the software world, high-profile developers are [taking sides][torvalds] in a civil war over LLM use. The FOSS community, which I think stands to gain the most from this revolution, has several big projects taking defensive measures in this perceived war. [Gentoo][gentoo], [NetBSD][netbsd] and [QEMU][qemu] all disallow LLM-generated contributions, and some projects even apologise for whatever has already slipped in. The Linux kernel is a notable exception, with a [more measured approach][kernel] to AI use.

But what prompted this article wasn't even about software.

I started bouldering a little under a year ago and went looking for a reference book on technique. I bought a couple of highly recommended books, such as [The Climbing Bible][climbing-bible], but they weren't quite what I wanted. Most of the good tips I found came from YouTube videos and random blog posts, so I tried an experiment: I had a group of LLM agents research what's out there on the web and write a book tailored to my needs. The result is honestly remarkable (to me, at least). It is, of course, exactly the book I was looking for.

Since it works as a general reference book (despite being tailored to me), I [open-sourced it][book] and shared it in a few bouldering communities on Reddit. It turns out that people **really** don't want to engage with an AI-generated book. I assumed that being upfront about the AI use would at least make people curious, but the disclosure probably made the reaction even more negative than it would otherwise have been.

So I don't blame people who keep their AI use to themselves. The distrust may be natural, but the reactions are usually irrational and often out of line. Fatigue is one thing, but for a subset of people, refusing to even consider anything made with the help of AI has become the norm. I suspect this subset will shrink over time into an ever smaller and more radicalised minority.

One kind of AI use that I do object to is when people act as so-called [meat proxies][meat-proxy], relaying LLM output verbatim when someone asks them a question. Here, the [AI;DR][aidr] moniker fits well.

At some point we will emerge from this unsteady state of things. The civil war will end. The anti-AI counterculture will be small and irrelevant. But I'm not sure we are psychologically ready for a world where we can create things at such an unnatural speed. My bouldering book came out yesterday and is already on its second edition. I edited it, and even I am not sure how I feel about that fact.

[vibe]: https://en.wikipedia.org/wiki/Vibe_coding
[purity-test]: https://www.youtube.com/watch?v=eDNuf4Zhk5I
[torvalds]: https://www.theregister.com/2026/01/08/linus_versus_llms_ai_slop_docs/
[gentoo]: https://wiki.gentoo.org/wiki/Project:Council/AI_policy
[netbsd]: https://www.netbsd.org/developers/commit-guidelines.html
[qemu]: https://www.qemu.org/docs/master/devel/code-provenance.html#use-of-ai-generated-content
[kernel]: https://docs.kernel.org/process/coding-assistants.html
[climbing-bible]: https://www.adventurebooks.com/products/the-climbing-bible
[book]: https://github.com/simongray/ReadingTheWall/releases
[meat-proxy]: https://gruhn.me/blog/2026-08-03/
[aidr]: https://www.rickmanelius.com/p/aidr-ai-didnt-read
