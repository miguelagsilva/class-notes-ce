*2026-02-10 05:20:18*

![[Pasted image 20260210052021.png]]

![[Pasted image 20260210052053.png]]

gpg --gen-key
gpg -a --export uc2023221244@student.uc.pt
gpg --import jgranjal.asc
gpg --edit-key jgranjal@gmail.com
sign
trust
5
gpg -sea -r jgranjal@gmail.com message

gpg -a -export jgranjal@gmail.com