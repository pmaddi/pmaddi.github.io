---
layout: post
title:  "Food for Auth"
categories: mozilla intern
excerpt: "
"
---

How do you know that the person logging into your system is the real user? _Multi-Factor Authentication_.

According to [wikipedia](https://en.wikipedia.org/wiki/Multi-factor_authentication):
> Multi-factor authentication (MFA) is an approach to authentication which requires the presentation of two or more of the three independent authentication factors: a knowledge factor ("something only the user knows"), a possession factor ("something only the user has"), and an inherence factor ("something only the user is")

The knowlege factor is straightforward--use a password. And remember not to [roll your own.](https://crackstation.net/hashing-security.htm)

Over the web though, inherence factors such as fingerprints, DNA, and blood vessel patterns are out of the question.

Since wikipedia says we need at least two factors, lets focus on the possesssion factor. Get a secure key to your user to verify identity. Sounds simple, but ...

This means that you need to get a key to your user via a secure system.

Normally, MFA systems use a cellphone as the _possession factor_. 






# Food Factor Auth



We deliver a random order to you, and you type in what you got.



	Doesnt require a phone
	Ensures you're in the right location
	You can't get on <service> for another 30-60 mins
	You get food
	Relies on the food delivery network to get you your food

	
