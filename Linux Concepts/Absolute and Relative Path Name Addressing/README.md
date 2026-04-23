Një nga pikat e forta të punës me skedarët nga linja e komandës në Linux është fleksibiliteti dhe shumëllojshmëria e opsioneve që kemi si përdorues. Disa mund të thonë se shumë zgjedhje e bëjnë më të vështirë të dish mënyrën e saktë ose të gabuar për të kryer një veprim, por të tjerë (përfshirë edhe mua) do të argumentojnë se shpesh nuk ka një mënyrë perfekte për të kryer një detyrë, por vetëm mënyra të përsosura14.

Ajo që duhet të mbahet mend është se mënyra që zgjedhim për të kryer një detyrë duhet të përshtatet me detyrën dhe kontekstin. Në këtë kuptim, në Linux ka shumë opsione dhe kjo është veçanërisht e vërtetë kur bëhet fjalë për procesin e specifikimit të vendndodhjeve të skedarëve.

## Pathnames

Një pathname përfaqëson një varg teksti që vepron si një tregues drejt një skedari ose direktorie. Pathname-i i mëposhtëm tregon skedarin foo.txt i cili ndodhet brenda direktorisë pi, e cila vetë ndodhet brenda direktorisë home:

```
/home/pi/foo.txt
```
Karakteri i vetëm “special” ose i rezervuar kur përdoret një pathname është slash-i përpara (/). Ky karakter përdoret vetëm për të ndarë direktoritë dhe emrat e skedarëve sipas rastit.

Direktoritë dhe emrat e skedarëve zakonisht kufizohen në 255 karaktere, ndërsa gjatësia totale e një path-i kufizohet në 4096 karaktere. Për kontekst, deri në këtë pikë të kapitullit ka afërsisht 1500 karaktere.

```
Adresimi me Absolute Path Name
```

Një pathname absolut gjithmonë fillon nga direktoria root (/). Është një detaj interesant që shpesh njerëzit e identifikojnë direktorinë root si slash-in përpara, kur në fakt ajo i referohet një direktorie pa emër që ndodhet në anën e majtë të shenjës / (duke kujtuar se nuk mund të përdoret / brenda emrave të direktorive ose skedarëve).

Më poshtë është një pathname absolut për skedarin foo.txt i cili ndodhet brenda direktorisë pi, e cila ndodhet brenda home, e cila është brenda direktorisë root:

```
/home/pi/foo.txt
```

## Adresimi me Relative Path Name

Një pathname relativ është ai ku vendndodhja e skedarit ose direktorisë merret në raport me direktorinë aktuale ku ndodhet përdoruesi.

Për shembull, nëse jemi në direktorinë home/pi (direktoria “home” e përdoruesit pi) dhe duam të listojmë (ls) skedarin foo.txt, mund të përdorim adresimin absolut:

ls /home/pi/foo.txt

Megjithatë, duke qenë se jemi në /home/pi, mund të përdorim adresim relativ dhe thjesht të shkruajmë:

```
ls foo.txt
```
Për të përdorur në mënyrë efektive adresimin relativ, duhet të dimë si të ngjitemi në hierarkinë e direktorive (zbritja bëhet thjesht duke shkruar emrin e direktorisë). Ngjitja në direktorinë prind bëhet me karakteret .. (pikë pikë).

Nëse imagjinojmë se jemi përsëri në /home/pi dhe duam të listojmë skedarin bar.txt që ndodhet në /home/raspberry, mund të shkruajmë:

```
ls ../raspberry/foo.txt
```
Këtu karakteret .. na çojnë fillimisht një nivel më lart në direktorinë home dhe më pas hyjmë në direktorinë raspberry.

## Short-cut “home”

Karakteri tilde (~) përdoret si një shkurtim për të treguar direktorinë home të një përdoruesi. Pra, duke supozuar se përdoruesi ‘pi’ ka direktorinë home /home/pi, por ne jemi në direktorinë /tmp, mund të listojmë skedarin foo.txt duke përdorur këtë shkurtesë:

```
ls ~/foo.txt
```