---
title: nontransitive_voting
description: 'A Ruby-on-Rails web app for a community to vote on large pools of candidates.'
rank: 4
external_url: https://github.com/dividedharmony/nontransitive_voting
external_location: GitHub
parent:
  name: "Programming"
  href: "/programming"
---

This web application uses the [Ruby on Rails](https://rubyonrails.org/) web framework and [PostgreSQL](https://www.postgresql.org/) as its database language.

The core idea of the `nontransitive_voting` app is to allow a community to vote on the "best" candidates out of a wide and varied pool of possibilities. Rather than utilizing existing voting methods such as [First-past-the-post](https://en.wikipedia.org/wiki/First-past-the-post_voting) or [Ranked Choice](https://ballotpedia.org/Ranked-choice_voting_(RCV)), this app utilizes its own voting method called "Non-transitive Pairwise-Comparison Voting" or NTPC Voting.

### Why not use other voting methods?

The problems with other voting methods are numerous and well-documented. Most prominently, [Arrow's Impossibility Theorem](https://plato.stanford.edu/entries/arrows-theorem/) states that when voters are given when voters have three or more distinct alternatives (options), no ranked voting electoral system can convert the ranked preferences of individuals into a a complete and transitive community ranking while also meeting a specified set of criteria:

- If every voter prefers A over B, then the community ranking should rank A over B
- Even when alternatives like C or D are introduced, if voters continue to prefer A over B, the community ranking should continue to rank A over B. This is known as "Independence from Irrelevant Alternatives" (IIA).
- No single voter should possess the power to determine the community ranking.

### What is Non-transitive Pairwise-Comparison (NTPC) Voting?

To sidestep Arrow's Impossibility Thereom, NTPC explicitly does not attempt to represent voter's preferences as transitive. Instead, voters are presented with pairings of all combination of options and for each pairing, the voter indicates which option they prefer. This means that a voter can express that they prefer A over B, B over C, and C over A.

NTPC determines a winner by counting each time a candidate was preferred over an alternative and whichever candidate has the highest count wins the vote. This counting method violates Independence from Irrelevant Alternatives, but since preferences are not considered transitive, independence cannot be assumed.

For further reading, the Standford Encyclopedia of Philosophy has entries on the [transitivity of preferences](https://plato.stanford.edu/entries/preferences/#Tra) and on [voting methods](https://plato.stanford.edu/entries/voting-methods/).

### Applications of NTPC

The greatest weakness of NTPC is the time it takes for a voter to fill out their vote as the number of pairwise comparisons needed to make is exponentially related to the number of candiates in the voting pool. However, every voter does not need to fill out every pairwise comparison, as ones left blank can be considered votes of indifference that count for neither candidate.

While this feature makes NTPC difficult to recommend for practical elections, it is perhaps the greatest strength for user engagement within the context of a web application. While a first-past-the-post poll (like those seen on [Twitter](https://help.twitter.com/en/using-twitter/twitter-polls)) can engage a user for a couple seconds, an NTPC vote with a pool of even a dozen candidates could represent hours of interaction per user.

With this in mind, the `nontransitive_voting` web app was originally designed to allow users participate in an NTPC vote to determine "best anime of the year" for the anime-watching community to act as a competitor to [Crunchyroll's Anime Awards](https://www.crunchyroll.com/animeawards/index.html).

Future commits may extract the NTPC logic into a generic engine that can be used to plug into a web app. It can then be the responsibility of the web app to specify what type of candidates are being compared.
