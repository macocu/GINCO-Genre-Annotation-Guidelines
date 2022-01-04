---
layout: entry
title: Guidelines for Manual Checking of the Web Corpora
---

The purpose of task is to detect low quality domains which can be removed before we continue with additional processing of the corpora.

For each domain, there is a link to the live site and a link to random triples of sentences in context to see the actual content of the sites in Sketch Engine. We thoroughly check just the top 300 to 1500 domains. Other, smaller domains are checked only in the case when their name is suspicious, usually not in the national TLD or containing suspicious words, e.g. "cz.flirtydolls.com".

## Table of contents
* [What do we check?](#what-do-we-check)
* [Steps](#steps)
* [Solved dilemmas](#solved-dilemmas)
* [Topics](#topics)


## What do we check?
* machine translation (more details on how to recognize it [here](_pages/machine_translation.md)).
* generated text ([examples](_pages/generated_text_examples.md))
* foreign language
* lists (no full sentences) ([examples](_pages/non-textual_examples.md))
* HTML Source Code/Markdown ([examples](_pages/markdown_examples.md))

## Steps

1. Read the examples from the domain:
	* The top 20 domains should be thoroughly checked:
		1. open the live website (column B), check whether it looks like it's a machine translation (unusual menu items names, an option of choosing a translation in many languages)
		2. read all of the concordances in the Sketch Engine (column C), looking for machine translation, generated text, foreign language, lists (no full sentences), HTML source sode or markdown (unusual elements in the running text)

	* For the remaining domains skimming through the first 15 concordances is enough, checking for the same as above
<br/>
2. Mark the domain as *ok*, *unsure*, *lq* (low quality), *bad* or *issue* (column D):
* if there are **no issues** -> *ok*
* if most of the concordances are **repeated text** (such as shipping conditions), text regarding **cookies** ([examples](_pages/cookies_examples.md)) -> *unsure* + add a note *"cookies"* or *"duplicated"* (these examples need to be checked again after the deduplication process which will remove the repeated text) (column E)
* if there are **encoding issues** -> *unsure* + add a note *"encoding"* (these examples will be checked after additional text processing (fixing the text with the Monocleaner tool))
* if there are issues with **HTML source code/markdown** --> *unsure* + add a description what can be done, e.g. "remove \<br/> tags", "remove all pages with "&diff=" or "action=edit" in the URL" (column F)
* if there are **some issues**, but the majority of page is okay -> *lq* + add a note which issue is present (column E)
* if the text could be **machine translation**, but you are not sure -> *lq* + note "possible machine translation" (column E)
* if there are **mostly issues**, i.e. more than half of the text contains issues / at least 2 concordances contain machine translation (you feel it is highly likely that the whole domain is machine translated) -> *bad* + add a note what is the issue (column E)
* if you encountered a phenomena not described in the guidelines and don't know what to do -> *issue* + add a note describing the phenomena, and open (an issue)[https://github.com/macocu/Manual-Checking-Web-Corpora-Guidelines/issues] on the GitHub 
<br/>
3. (Optional) Add information on topic (if there are multiple topics, leave empty):
* choose from the [proposed topic labels](#topics), if there are additional broad topics present in multiple domains, you can add them
<br/>
4. (Optional) Add information on genre if all concordances are in the same genre. Choose from the following labels (if none is applicable, leave empty):
* news portal
* legal/regulation - legal texts
* recipe
* forum
* promotion of services - all texts promote services of companies
* e-shop (includes platforms that provide accomodation (e.g. Booking/AirBnB-like content))
* research article (abstracts, theses, research articles)
* opinion (blogs, petitions - author's opinion is very obvious, visible)
* literature (prose, poetry, drama)
* small ads (advertisement websites where users post their ads)
<br/>
5. (Optional) If the language on the page seems **unedited** (many typos) or **non-standard** (very informal language, such as in forums), mark that by *Y* in column I

Mark only sites that were checked - content with an empty value in column D is considered unchecked and will be kept in the corpus.

## Solved dilemmas

* dictionary entries -> *bad* (not textual, foreign language, old varieties of language)
* older varieties of language (e.g. in old literature) -> *bad* (if most of the text is written like this and the words are very different, otherwise *lq* + note)


## Topics

* academic (research articles, theses)
* animals
* beauty (including make-up, fashion, clothes, fabrics etc.)
* business (includes economy and finance)
* cars
* community (municipality sites, town sites)
* construction & real estate
* culture (books, theatre, opera)
* engineering (machines, machine parts, electroengineering etc.)
* environment
* entertainment (movies, music, events …)
* family (includes all topics/products connected to children)
* food & drinks (includes products involved in food preparation, e.g. dishes)
* gambling & casinos
* history (includes biographies)
* hobbies (shooting, gaming, railway enthusiasts etc. - sport hobbies are included in "sport")
* home & garden
* law
* love & sex
* politics
* public safety (fire-fighting, police, mountain rescue etc.)
* religion
* science (chemistry, medicine etc. - but not written in a form of a research article, thesis)
* services (includes job offers)
* sport (includes sport hobbies, e.g. hiking, yacting, cycling)
* technology (IT, programming, computers, phones, etc.)
* traffic
* travel
* well-being (physical, mental health; includes diets, fitness, wellness)