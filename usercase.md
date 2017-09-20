People
======

- Project owner (PO)
- Freelancer (F)

Issue broker
============

Issue broker (IB) is a collection of forms for user action + views + signals processor.


Forms:
- project owner adds new repo and sets hourly rate
- 

View:
- list all issues


Signals:
- listen to webhook for new issues
- listen to webhook for new issues

Services:
- pay the freelancer on event (issue closed) 


Context 
======

- Project owner and Freelancer are logged in issue broker with with  github accounts
- Project owner authorised payments from his paypal or other wallet

Scenario
========

1. Project owner: links project reposotory to issue brocker (with webhook)
1. Project owner: sets max hourly rate for repository (eg USD 10/h)
1. Issue broker app: starts monitoring new issues in repository (by webhook)
   - when found tagged issue (with ```[ib: 1:30h]``` pattern in title), save it to local database
1. Issue broker app: lists all tagged issues on main its page 
   - this view should read as ```repo name - issue title - hours - rate - status: open | closed | taken```
1. Freelancer: applies at issue brocker to do an open issue  
1. Project owner: selects freelancer
1. Freelancer: makes commits and issue comments at github
1. Project owner: makes issue comments at github
1. Project owner: closes issue
1. Issue broker app: monitors webhook to see issue closed
1. Issue broker app: makes payments from project owner to freelancer

Scenarion discussion
====================
- set hourly rate per issue, not per project
- reopening issue does not affect payment, can close only once
- can hacker want to send a fake issue close to webhook to release a payment?
