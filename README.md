# CSRF Attack Simulation – SEED Lab

## Author
Arlette Torres  
Lamar University – Computer Information Science

## Project Overview
This project demonstrates Cross-Site Request Forgery (CSRF) attacks against the Elgg web application in a controlled SEED Lab environment. The lab shows how attackers can exploit authenticated sessions using malicious web requests and how CSRF security tokens prevent these attacks.

## Environment
- Platform: SEED Ubuntu Virtual Machine
- Web Server: Apache
- Web Application: Elgg
- Host System: VirtualBox

## Objectives
- Perform a CSRF GET attack to add a malicious friend
- Perform a CSRF POST attack to modify a user profile
- Demonstrate successful attacks when protections are disabled
- Demonstrate how CSRF tokens prevent these attacks

## Attack 1 – CSRF GET Attack
A malicious HTML page was created that sends a forged GET request to the Elgg application:

/action/friends/add?friend=43

This request was triggered using a hidden image tag. When the victim visited the attacker page while logged in, the request executed automatically and added the attacker as a friend.

## Attack 2 – CSRF POST Attack
A hidden HTML form was created that automatically submitted a POST request to modify a victim profile.

The attack changed the profile description to:

"Boby is my Hero"

The attack executed automatically when the page loaded.

## Security Defense Tested
The Elgg CSRF protection mechanism was enabled using:

- __elgg_ts (timestamp token)
- __elgg_token (security token)

After enabling these protections, both attacks failed because the attacker page could not generate valid tokens.

## Key Cybersecurity Concepts
- Cross-Site Request Forgery (CSRF)
- Web application vulnerabilities
- Session authentication risks
- Token-based request validation
- Same-Origin Policy

## Tools Used
- Ubuntu Linux
- VirtualBox
- Apache Web Server
- HTML and JavaScript
- curl and grep

## Learning Outcome
This project provided hands-on experience with web security vulnerabilities and demonstrated how proper server-side protections prevent CSRF attacks.

## Report
See the full lab documentation in:

CSRF-SEED-Lab-Report.pdf
