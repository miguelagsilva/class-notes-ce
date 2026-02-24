*2026-02-10 09:21:31*
![[Pasted image 20260210032428.png]]

Ficha during class are not evaluated.
Only practical assignments are evaluated.

## Planning
![[Pasted image 20260210032559.png]]

## Evaluation
![[Pasted image 20260210032618.png]]

## Bibliography
![[Pasted image 20260210033018.png]]

## T1
### Assymetric encryption
Used to encrypt small blocks of data such as encryption keys hash functios values used in digital signatures. Public and private keys.
### Symetric encryption
Used to encrypted any size of datam encryption keys encrypt and also decrypt.
### Integrity Algorithm
Used to keep integrity of blocks of data from malicious changes.
### Authentication protocols
Based on cryptographic algorithms made to authenticate the identity of entities.

## CIA Triad
Confidentiality:
- Ensures that private or confidential data is not accessed by unauthorized individuals.
- Privacy: controls what information is collected and who it is shared with. GDPR
Integrity:
- Ensures information and programs are only changed in a specified and authorized manner.
Availability:
- Ensures that systems work in a timely manner and the service is not allowed for unauthorized users.

*RFC*
*Defines protocols or terms*

## [RFC 4949](https://www.rfc-editor.org/rfc/rfc4949) - Internet Security Glossary version 2
![[Pasted image 20260210034652.png]]

Both in **X.800** and [RFC 4949](https://www.rfc-editor.org/rfc/rfc4949) there are two types of attacks:
- Passive: Tries and get the information on the system but does not change it. Eg: trying to crack WPA2 encryption keys captured through sniffing.
- Active: Tries and change resources on the system or change it  

## [X.800](file:///home/miangosi/Downloads/T-REC-X.800-199103-I!!PDF-E.pdf) vs [RFC 4949](https://www.rfc-editor.org/rfc/rfc4949)
![[Pasted image 20260210034928.png]]

### Active attacks
Repetition:
- Passive capture of data and retransmission to try to produce a non authorized access.
Masquerade:
- Happens when an entity tries to look like another one. Often used in combination with other methods. Example: IP Spoofing
Changing of messages:
- Part of a legitimate message is changed, delayed or reorganized. Eg: MITM
Denial of service:
- Stops or inhibits the management of infrastrucure

![[Pasted image 20260210040730.png]]

## Non repudiation
![[Pasted image 20260210040746.png]]
Stops sender from denying sending a message, non repudiation ensures verifiable proof of origin and reception of a message. Ensure both ways that sender sent and receiver received. EG: PGP in emails.

## Attack surface
Composed of the vulnerabilities that can be explored in a system.
Examples:
- Open ports in web servers and other servers exposed to the outside and the code running on those ports.
- ...

## Audits
Automated software that enumerates threats and shows the attack surface on a system so a Summary can be made to fix it later.

## General model for security
![[Pasted image 20260210042251.png]]
![[Pasted image 20260210042453.png]]