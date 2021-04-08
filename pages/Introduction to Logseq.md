---
title: Introduction to Logseq
---

## https://raw.githubusercontent.com/logseq/logseq/master/resources/img/logo.png
## **Hello, everyone!**
Thank you for having me, so excited to share Logseq with you guys!
## **A little about the me**
I live in Hangzhou, my wife and I have a beautiful daughter :)
## **What's Logseq?**
### 1. At present, it's a non-linear, outliner notebook for organizing and sharing your personal knowledge base.
### 2. By the end of this year, Logseq can be used for real-time knowledge collaboration
### 3. The long-term goal is to help children and more people to connect their thoughts with the past and the future
## **Why building logseq?**
### I've been dreaming about a ^^TiddlyWiki^^ with ^^Org-mode^^ and Outliner, also I want to make it easier to use so that I can use it with my 5-years old daughter. She already have many draws inside my graph!
## **What's the difference between logseq and other tools?**
### **The user is the king of the data. ** 
Simply put, I don't trust putting my notes and my life on any cloud services without End-to-End encryption support, at least it should be built "local-first"
### **Logseq doesn't lock the data.**
#### Even though logseq is an outliner tool, it works directly with plain-text like Markdown and Org mode. We believe in plain-text for data longevity, we believe in standard syntax and open protocols for better collaboration with the existing ecosystem.
### **Everyone can build their own workflows**
Slip box? GTD? Hierarchical tags? With [[Queries]], [[Advanced Queries]] and coming plugins, everything seems to be possible :)
### **Open Source**
As developers, we believe the ultimate fun is to fork the code and do nasty tweaks!
### **Being different instead of a clone**
#### Yeah, we copied some ideas and UX from Roam Research, but trust me Roam are copying from Logseq too, e.g.
##### 1. `/Draw` command
##### 2. ` /Page Embed` [[Excalidraw]]
##### 3. One-way sync from the database to Markdown (two-way sync is on their roadmap now)
#### We're trying to provide the best privacy and user experience, here are some "new" things we've been working on so far!
#### 1. Logseq might be The **_first_** app that have ^^two-way sync between plain-text and the outliner^^.
#### 2. Org-mode made easy! People don't have to learn Emacs to just try it
#### 3. Bring org mode's task management to Markdown
#### 4. Sync your notes with Git on the Web, logseq server doesn't store the notes
#### 5. New **Chrome Native File System API** to read and write files directly from the local file system
#### 6. `Now Later workflow`
##### It's inspired by Joe Armstrong's article to Triage Systems at [Fun with the TiddlyWiki](https://joearms.github.io/#2018-12-26%20Fun%20with%20the%20TiddlyWiki)
#### 7. Custom queries on journals page (demo)
#### 8. Publishing the whole graph to your own website, just like this one
https://tiensonqin.github.io/
## **The tech we used**
### The web app is using [[Clojurescript]]
#### Why?
##### Clojure as a lisp language gives us a nice REPL which can be used to query and modify the app's state, it's both enjoyable and faster for development
##### Both Clojure and Clojurescript are very stable, my old code several years ago can still run without any issues
### [[OCaml]] for parser
#### 1. https://github.com/mldoc/mldoc
#### 2. mldoc uses [Angstrom](https://github.com/inhabitedtype/angstrom) 
> Angstrom is a parser-combinator library that makes it easy to write efficient, expressive, and reusable parsers suitable for high-performance applications.
### [[Datascript]]
> Immutable database and Datalog query engine for Clojure, ClojureScript and JS
#### Some Datalog queries
##### 
#+BEGIN_SRC clojure
[:find (pull ?b [*])
 :where
 [?p :page/name "excalidraw"]
 [?b :block/ref-pages ?p]]
#+END_SRC 

#+BEGIN_QUERY
{:title "Blocks referenced to Excalidraw"
  :query [:find (pull ?b [*])
               :where
               [?p :page/name "excalidraw"]
               [?b :block/ref-pages ?p]]}
#+END_QUERY
#### Oh I don't want to write the raw Datalog queries, what can I do?
##### {{query [[Excalidraw]] }}
#### More examples:
##### Blocks referenced either `Clojurescript` or `OCaml`
{{query (or [[Clojurescript]] [[OCaml]])}}
##### All `LATER` tasks with the `A` priority
{{query (and (todo LATER) (priority A))}}
##### {{query (and (property type project) (not (property template)))}}
## **The future**
### Logseq will switch to beta testing at the end of this month (it's in alpha testing now).
:PROPERTIES:
:now: 1617893295248
:END:
Which means all the file corruption issues will be fixed and we'll have better undo && redo
### Real-time collaboration and hopefully with End-to-End encryption
### Collaborate with OSS projects and teams for better web safety
### LATER [#A] Exploring more ways to help for thoughts and knowledge collaboration
:PROPERTIES:
:later: 1617893339747
:END:
## **Thank you all for joining the meeting, any questions are appreciated!**
