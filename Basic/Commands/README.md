# Commands

## Wildcards

Një koncept i rëndësishëm për t’u kuptuar në Linux është përdorimi i wildcards.

Në një kontekst sportiv, një “wildcard” është një lojtar ose element që mund të përdoret si zëvendësues. Ai nuk ka domosdoshmërisht një rol të fiksuar, por mund të përfaqësojë ose të zëvendësojë një grup të gjerë elementësh standardë.

Në Linux, wildcards janë një veçori e command line, që e bëjnë atë shumë më fleksibël krahasuar me menaxhuesit grafikë të file-ve (file managers). Përdoruesit që kanë provuar kombinime komplekse të tasteve Shift / Ctrl dhe klikime me mouse gjatë organizimit të file-ve në GUI e dinë që kjo mund të bëhet e vështirë dhe jo efikase.

Për shembull, nëse kemi një directory me shumë file dhe subdirectories, dhe duhet të zhvendosim të gjithë file-t Python (me prapashtesën .py) që përmbajnë fjalën “pi” në emër, në një directory tjetër, kjo mund të jetë një detyrë që kërkon shumë kohë në mënyrë manuale.

Në command line në Linux, kjo detyrë bëhet pothuajse aq e thjeshtë sa zhvendosja e një file-i të vetëm. Kjo është e mundur falë wildcards.

Wildcards janë karaktere speciale që lejojnë përzgjedhjen e emrave të file-ve që përputhen me një model (pattern) të caktuar karakteresh. Kjo na mundëson të zgjedhim shumë file njëherësh duke shkruar vetëm disa karaktere.

Në shumicën e rasteve, përdorimi i wildcards është më i shpejtë dhe më efikas sesa përdorimi i një file manager-i grafik.

* Me posht jan wildcards me te perdorurat 
```Wildcard Matches
* zero or more characters
? exactly one character
[abcde] exactly one of the characters listed
[a-e] exactly one character in the range specified
[!abcde] any character that is not listed
[!a-e] any character that is not in the range specified
{pi,raspberry} exactly one entire word from the options given
```
