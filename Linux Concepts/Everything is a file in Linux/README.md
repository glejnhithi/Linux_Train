# Everything is a file in Linux

Një frazë që shpesh do të dëgjohet në bisedat për Linux është se;
```
    Everything is a file
```
Për dikë të ri në Linux, kjo tingëllon si një lloj “shakaje të brendshme” që është krijuar për të frikësuar përdoruesit e rinj dhe ndonjëherë mund të bëhet një pengesë për një kuptim më të thellë të filozofisë që qëndron pas mënyrës së zhvillimit të Linux-it.
Shpjegimi pas kësaj deklarate është se Linux është projektuar si një sistem i ndërtuar nga një grup pjesësh që ndërveprojnë me njëra-tjetrën, dhe mënyra se si këto pjesë komunikojnë është përmes një metode të përbashkët. Kjo metodë është përdorimi i një skedari si bllok ndërtimi i përbashkët dhe të dhënat në një skedar si mekanizëm komunikimi.
Truku për të kuptuar kuptimin e “Everything is a file” është të zgjerojmë kuptimin tonë se çfarë mund të jetë një skedar.

## Skedarët tradicionalë
Koncepti tradicional i një skedari është një objekt me një emër specifik, në një vendndodhje specifike dhe me një përmbajtje të caktuar. Për shembull, mund të kemi një skedar të quajtur foo.txt që ndodhet në direktorinë /home/pi/ dhe mund të përmbajë disa rreshta teksti si më poshtë;
```
This is the first line
This is the second line
```

## Direktori
Sado e çuditshme të duket, edhe një direktori është një skedar. Aspekti i veçantë i një direktorie është se ajo është një skedar që përmban një listë informacioni për skedarët (dhe/ose nën-direktoritë) që ajo përmban.
Pra, kur përdorim komandën ls për të listuar përmbajtjen e një direktorie, në të vërtetë ajo që ndodh është që sistemi operativ merr informacionin e duhur nga skedari që përfaqëson atë direktori.

## Informacion i sistemit
Megjithatë, skedarët mund të jenë edhe kanale informacioni. Direktoria /proc/ përmban skedarë që përfaqësojnë informacion të sistemit dhe proceseve. Nëse duam të marrim informacion për llojin e CPU-së që po përdor kompjuteri, skedari cpuinfo në /proc/ mund ta tregojë këtë. Duke ekzekutuar komandën cat /proc/cpuinfo mund të shfaqim një sasi të madhe informacioni për CPU-në (më poshtë është një pjesë e atij informacioni);

```
pi@raspberrypi ~ $ cat /proc/cpuinfo
processor : 0
model name : ARMv7 Processor rev 5 (v7l)
BogoMIPS : 57.60
Features : half thumb fastmult vfp edsp neon vfpv3 tls vfpv4 idiva idi\
vt vfpd32 lpae evtstrm
CPU implementer : 0x41
CPU architecture: 7
CPU variant : 0x0
CPU part : 0xc07
CPU revision : 5
Hardware : BCM2709
Revision : a01041
Serial : 000000002a4ea712
```
Ndoshta në këtë fazë kjo nuk do të thotë shumë, por nëse do të shkruanim një program që ka nevojë për një lloj specifik CPU-je për të funksionuar me sukses, ai mund të kontrollonte këtë skedar për të siguruar që mund të ekzekutohet si duhet. Ka një gamë të gjerë skedarësh në /proc/ që përfaqësojnë shumë informacione rreth mënyrës se si po funksionon sistemi.

## Pajisjet
Kur përdorim pajisje të ndryshme në një sistem operativ Linux, edhe ato përfaqësohen si skedarë. Në direktorinë /dev/ kemi skedarë që përfaqësojnë një gamë pajisjesh fizike që janë pjesë e kompjuterit tonë. Në sisteme më të mëdha me disa disqe, ato mund të përfaqësohen si /dev/sda1 dhe /dev/sda2, kështu që kur duam të kryejmë një veprim si formatimi i një disku, përdorim komandën mkfs mbi skedarin /dev/sda1.
Direktoria /dev/ gjithashtu përmban disa skedarë të veçantë që përdoren si mjete për gjenerimin ose menaxhimin e të dhënave. Për shembull, /dev/random është një ndërfaqe për pajisjen e kernel-it për numra rastësorë. /dev/zero përfaqëson një skedar që vazhdimisht transmeton zero (edhe pse kjo mund të duket e çuditshme, mund të përdoret kur duam të mbishkruajmë një pjesë të diskut për ta fshirë). Më i njohuri nga këta skedarë të veçantë është ndoshta /dev/null15. Ky funksionon si një “pajisje null” që në thelb hedh poshtë çdo informacion.