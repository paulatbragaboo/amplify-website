# 2. Host website in AWS Amplify

Date: 2022-10-10

## Status

Accepted

## Context

To host a new static business website for Bragaboo.
There is desire to deepen AWS skills and use this as an opportunity to gain hands on experience in the team.
The choice for static website is S3 as a website, exposed via Cloudfront.
- This means manual upload of each file. 
Or, could be written as static files behind a (e.g.) Node.js/Express Server on EC2
- For a statis website, creating a Server is overkill. (That WAs done on Popcron - because we hosted website which then signed into and Backbone App)
- You still have to provide ports, SSL certs etc.
Or, use AWS Amplify:
- This provides auto deply on push to a branch for easy fo deployment
- All files are backed by Cloudfronts so iages can be handled diret within the code folder
- AWS Ampify allows to configure DNS for a domain, so we get full Https/SSL included for free.

- Additional drivers are:
  -- What is easy
  -- What is fast
  -- What is low cost
 

## Decision


We've selected AWS Amplify. 

## Consequences

This provides:
- ease deplpyment on push to Git
- SSL and cloudfront 
- easy DNS setup

Concerns:
- Roue 53 may be better as Godaddy does not suppore ANAME or ALIAS records for root 'bragaboo.com' domain. Thhe workarund is soft DNS forwarding 302 to www. subdomain.   But this leave a gap for HTTPS to root domain which does not forward.

Future:
Moev DNS from GoDaddy to Route53.


