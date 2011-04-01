---
layout: post
title: Importance of Terminology
---

Recently, I came across [an article](http://www.techcrunch.com/2009/04/02/with-hadoop-amazon-adds-a-web-scale-file-system-to-its-cloud-computer) on TechCrunch, 
which reported on Amazon's recent addition of Hadoop to their cloud infrastructure. I won't go into what all of this means as there is a differnet point I want to make.
The author of this article mistakenly called MapReduce a file system, which isn't entirely correct. Readers were quick to point out the mistake (myself included), 
with some responses being rather harsh. Why would readers react so strongly to a misuse of terminology that is entirely understandable if you have not had intimate experience 
with the technology in question?

The reason for such a reaction is simple. For a developer, using the correct terminology when describing and discussing his / her work is crucial. If the wrong terminology is 
used, then grave misunderstandings can result, which could easily lead to rather disastrous consequences. To use another example, I recently attended 
[VoCamp Austin](http://vocamp.org/wiki/VoCampAustin2009), which was a technology meetup to discuss Semantic Web technology. During the meetup it became exceedingly clear that 
a number of the attendees had a poor grasp of the terminology used to describe Semantic Web concepts. Terms such as triples, ontology, semantics, structured data, linked data, 
schemas, RDF, OWL, and XML were thrown around, often incorrectly. 

The improper use of terminology when discussing something as involved as the Semantic Web introduces a large communication barrier when developers interact. My definition of 
linked data may differ from yours, and when I describe the role of linked data in my application, you will be utterly confused. In the worst case, the term will mean something 
utterly different to you, and if you are using my description as the foundation for developing your application, then your implementation will be fundamentally flawed. The cost 
of such miscommunication may be subtle, but the consequences can be disastrous, such as in the case of the [Mars Climate Orbiter](http://en.wikipedia.org/wiki/Mars_Climate_Orbiter), 
where certain values were communicated incorrectly, and one team understood the values to be in metric, while others understood the values to be in the imperial system.

Lesson learned? When discussing something of significant complexity and substantial inherent terminology, be sure to make the definitions of the terminology used absolutely clear. 
This may sometimes require your audience to forget their existing definitions, and you should be extra cautious when introducing terminology that uses common words or is 
borrowed from other terminology.
