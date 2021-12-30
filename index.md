---
layout: entry
title: Guidelines for Manual Checking of the Web Corpora
---

The purpose of task is to detect low quality domains which can be removed before we continue to additional processing of the corpora.

For each domain, there is a link to the live site and a link to random triples of sentences in context to see the actual content of the site in Sketch Engine. We thoroughly check just the top 300 to 1500 sites. Other, smaller sites are checked only in the case when their name is suspicious, usually not in the national TLD or containing suspicious words, e.g. "cz.flirtydolls.com".

## Table of contents
* [What do we check?](#what-do-we-check)
* [Steps](#steps)
* [Topics](#topics)
* [Solved dilemmas](#solved-dilemmas)


## What do we check?
* machine translation (more details on how to recognize it [here1](_pages/machine_translation.md)).
* generated text ([examples](_pages/generated_text_examples.md))
* foreign language
* lists (no full sentences) ([examples](_pages/non-textual_examples.md))
* HTML Source Code/Markdown ([examples](_pages/markdown_examples.md))

## Steps

1. Read the examples from the domain:
	* The top 20 pages should be thoroughly checked:
		1. open the live website (column B), check whether it looks like it's a machine translation (unusual menu items names, an option of choosing a translation in many languages)
		2. read all of the concordances in the Sketch Engine (column C), looking for machine translation, generated text, foreign language, lists (no full sentences), HTML source sode or markdown (unusual elements in the running text)

	* For the remaining pages skimming through the first 10 concordances is enough, checking for the same as above

2. Mark the domain as *ok*, *unsure*, *lq* (low quality) or *bad* (column D):
* if there are **no issues** -> *ok*
* if most of the concordances are **repeated text**, text regarding **cookies** -> *unsure* + add a note *"cookies"* (these examples will be checked again after the deduplication process which will remove the repeated text)
* if there are **encoding issues** -> *unsure* + add a note *"encoding"* (these examples will be checked after additional text processing (fixing the text with the Monocleaner tool))
* if there are **some issues**, but the majority of page is okay -> *lq* + add a note, which issue is present. For the top 20 domains, if the issue is HTML Source Code or Markdown, add a description what can be done, e.g. "remove \</br> tags", "remove all pages that have "diff" in the URL name"
* if there are **mostly issues** -> *bad* + add a note what is the issue

Mark only sites that were checked - content with an empty value in column D is considered unchecked and will be kept in the corpus.

3. (Optional) Add information on topic if you think that the whole domain is dedicated to just one topic:
* choose from the [proposed topic labels](#topics), if there are additional broad topics present in multiple domains, you can add them

4. (Optional) Add information on genre if all concordances are in the same genre. Choose from the following labels:
* legal/regulation - legal texts
* recipe
* forum
* promotion of services - all texts promote services of companies
* promotion of a product - all texts promote products (e-shop)

## Topics

* academic (research articles, theses)
* animals
* fashion (including make-up, beauty)
* cars
* construction & real estate
* culture (books)
* entertainment (movies, music, events …)
* business (includes economy and finance)
* food & drinks
* gambling & casinos
* history
* hobbies (hiking, shooting)
* home & garden
* engineering (machines, electroengineering etc.)
* family
* law
* environment
* animals
* politics
* products (various products in an e-shop)
* religion
* science (chemistry, medicine etc. - but not written in a form of a research article, thesis)
* love & sex
* services
* sports
* technology (IT)
* travel
* well-being (physical, mental health)


## Solved dilemmas

* dictionary entries -> ok
