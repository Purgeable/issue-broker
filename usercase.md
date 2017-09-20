People
======

- Project owner (PO)
- Freelancer (F)

Forms
=====

- Issue broker (IB) is a collection of forms for user action + signals processor 

Context 
======

- Project owner and Freelancer are logged in issue broker with with  github accounts
- Project owner authorised payments from his paypal or other wallet

Scenario
========

#. Project owner: links project reposotory to issue brocker (with webhook)
#. Project owner: sets max hourly rate for repository (eg USD 10/h)
#. Issue broker app: starts monitoring new issues in repository (by webhook)
   - when found tagged issue (with ```[ib: 1:30h]``` pattern in title), save it to local database
#. Issue broker app: lists all tagged issues on main its page 
   - this view should read as ```repo name - issue title - hours - rate - status: open | closed | taken```
#. Freelancer: applies at issue brocker to do an open issue  
#. Project owner: selects freelancer
#. Freelancer: makes commits and issue comments at github
#. Project owner: makes issue comments at github
#. Project owner: closes issue
#. Issue broker app: monitors webhook to see issue closed
#. Issue broker app: makes payments from project owner to freelancer


Simplifications 
===============
- no internal chat 
- no freelancer pages
