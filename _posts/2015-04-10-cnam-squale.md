---
layout: post
title: "Operation Squale au CNAM [fr]"
description: ""
category:
tags: []
---
{% include JB/setup %}
# Les "bonnes résolutions" du nouvel an
Pour passer le temps pendant cette période abhorrée des fêtes obligatoires, je cherche en général quelque chose pour m'occuper l'esprit pour le début de l'année. Cela a donné:

- En 2010, [La SEGA Megadrive dans un FPGA.](https://github.com/Torlus/fpgagen)

- En 2011, [La NEC PC-Engine dans un FPGA.](https://github.com/Torlus/FPGAPCE)

La [Jaguar dans un FPGA](https://github.com/Torlus/JagNetlists) a du naître dans ces moments-là aussi (en 2 fois, entre 2012 et 2013).

Et cette année, pas moyen de trouver l'inspiration. Et puis (allez savoir comment) je suis (re)tombé sur certaines pages parlant du **Squale**, un micro-ordinateur des années 80. Une machine aussitôt annoncée, aussitôt disparue.

Les informations à son sujet se résument en gros à ce que [Olivier Aichelbaum](http://www.acbm.com/) a écrit sur le sujet:

- [Squale, l'ordinateur qui s'est cassé les dents.](http://www.acbm.com/olivier-aichelbaum/musee/images/)

- [Les souvenirs du constructeur de l'ordinateur Squale.](http://www.acbm.com/inedits/squale-apollo-7.html)

Il n'en existe que *trois exemplaires* connus: celui d'Olivier, un autre appartenant à un collectionneur qui est resté sourd aux diverses sollicitations, et un dernier cédé au [CNAM](http://www.arts-et-metiers.net/) par [Sylvain Bizoirre](http://www.espace-turing.fr/Interview-Acquisition-par-le-CNAM.html).

Olivier étant plutôt du genre occupé, à l'étranger, et de retour en France de manière difficilement planifiable, la seule alternative "stable" restait le **CNAM**.

Toutes les tentatives précédentes ayant échoué, me voilà donc muni de la motivation nécessaire pour tenter ma chance.

# Prise de renseignements et démarche

## Prise de contact

Je commence à regarder du côté de la communauté des collectionneurs,
ou amateurs des micro-ordinateurs de cette époque. Je sais que des tentatives d'approche ont été réalisées, mais sans succès.

Je dépose donc une demande en ce sens sur le formulaire de contact du CNAM. Au bout de quelque temps, je reçois la réponse d'une personne que je nommerai **Ariane**.

En voici la teneur:

> Cette manipulation peut etre envisageable mais elle ne peut se faire que dans nos locaux a St Denis (93), et donc sur rendez-vous, en ma presence et celle d'un de nos restaurateurs.

> De plus, j'aurai souhaite de votre part, avant toute demande de rendez-vous, une description detaillee de votre procedure d'intervention afin de valider que celle-ci s'effectuera a priori sans risque pour l'objet.

Bonne nouvelle! L'intervention est envisageable, mais je décèle rapidement qu'il va falloir montrer "patte blanche", et se poser les bonnes questions dès le début. On ne plaisante pas avec la conservation et préservation du patrimoine, et c'est tant mieux.

Cependant, conserver un objet "matériel" est une chose, mais dans ce cas-là, ce qui nous intéresse (entre autres), ce sont aussi des parties "immatérielles", comme le contenu de l'EPROM contenant le moniteur, ainsi que le contenu d'un PAL.

## Analyse des informations existantes

J'en fais part à **Jeff** dont je perçois déjà que les compétences seront utiles pour mener une telle opération.

Nous mettons en commun nos informations sur le sujet, et voici ce qu'il en ressort:

- Le PCB est à double face, ce qui va permettre de le "capturer" complêtement.

- Tous les composants logiques sont montés sur support, ce qui est un excellente nouvelle. Pas de dessoudage/ressoudage à prévoir à priori.

- Il n'y a pas d'ASIC, le seul composant programmable est un PAL qui ne sert à priori qu'à faire du décodage d'adresses. On pourra donc en extraire facilement la combinatoire.

## Donner un sens à la démarche

Pour la partie technique, pas de grande difficulté, donc.

Cependant, la question qui m'a été posée un certain nombre de fois est: *Pourquoi?*

Cela m'a amené finalement à réfléchir sur le sujet (pour ma part, "parce que je peux" était une réponse satisfaisante). Et finalement, j'ai trouvé du sens à cette démarche:

- Ce genre d'opération sur une machine inconnue est relativement rare. Et ici, il faut ménager la chèvre et le chou: récupérer le logiciel peut avoir un impact sur le matériel. Dans l'hypothèse d'un choix à faire entre une préservation "en l'état" ou la récupération d'informations, tout le monde n'aura pas forcément la même opinion.

- La préservation de systèmes électroniques nécessite parfois des interventions, je pense notamment aux fuites de condensateurs qui peuvent détruire le PCB.

- Parallèlement à cette intervention, l'association [silicium.org](http://www.silicium.org) devait réaliser un workshop en Belgique sur la maintenance et réparation de micro-ordinateurs anciens, et sur l'extraction des programmes et données stockées sur supports "fragiles" (Diskettes, CD-ROMs...).

- La proximité de dates de ces deux événements ne pouvait pas être le fruit du hasard :) L'occasion me semblait belle pour réaliser un reportage sur le sujet.

Malheureusement, le manque de temps et les circonstances en ont décidé autrement...

Bon, entrons dans le vif du sujet, en passant à l'intervention proprement dite.

# Premier contact

**Yun**, ma compagne, et moi arrivons sur les lieux. Même si au cours de nos échanges avec **Ariane** j'avais compris qu'on ne plaisantait pas avec la sécurité, c'est tout de même surprenant de voir que les réserves du CNAM résident dans une sorte de bunker.

Une fois les contrôles de sécurité passés, nous sommes accueillis par **Ariane** qui nous amène dans une salle où nous attend le fameux (ou pas) ***Squale***.

![first](/images/first.jpg)

# Etude externe

L'arrivée de **Jeff** étant un peu retardée, je consacre mon temps aux travaux préliminaires, à savoir prendre quelques photos et procéder au repérage des composants.

![open](/images/open.jpg)

## Les photos de la carte mère

Ici on trouve le *CPU*, la *DRAM* associée, ainsi que l'*EPROM* contenant le moniteur, et un *PIA*.

![v3](/images/v3.jpg)

La machine dispose d'une connectique assez étoffée, on retrouve donc un deuxième *PIA*, ainsi qu'un *ACIA*. Le paquet de résistances en bas constitue certainement des *échelles R/2R* pour la *sortie vidéo*.

On y trouve aussi le *chip audio* (AY-3-8910A).

On trouve aussi un *ampli op* certainement utilisé pour la lecture de *cassettes*.

![v2](/images/v2.jpg)

Enfin on retrouve le *chip vidéo* semi-graphique, et sa *DRAM* associée.

![v1](/images/v1.jpg)

## Le repérage des composants

Bon ce n'est pas le travail le plus passionnant du monde, mais il faut bien que quelqu'un le fasse. On prend son mal en patience et ça donne ceci:

![n1](/images/n1.jpg)

![n2](/images/n2.jpg)

![n3](/images/n3.jpg)



Le descriptif des composants se trouve [ici](/images/mb.txt).

## L'arrivée de Jeff

**Jeff** arrive enfin, avec un paquet de matériel, ce qui n'est pas étonnant. :)

Le plus amusant reste son *dumper/émulateur d'EPROMs* sur base de PC accompagné d'une carte ISA dédiée. L'utilitaire logiciel tient sur une disquette, mais évidemment, le lecteur a été remplacé par un [HxC Floppy Drive Emulator](http://hxc2001.free.fr/floppy_drive_emulator/).

![dumper](/images/dumper.jpg)

Il apporte aussi un *scanner*, dans le but d'avoir une vision du PCB complète. Il suggère une autre idée: le PCB étant une pré-production, et étant translucide, il serait possible de compléter le scan des 2 faces par une photo du PCB *soumis à un forte lumière* afin de voir *les 2 faces en même temps*.

**Ariane** nous rappelle cependant que soumettre des matières plastiques à de fortes lumières
est contraire à la conservation sur le long terme.

Le temps nous a manqué pour prendre en considération ce problème, mais je ne doute pas
qu'avec les connaissances des uns et des autres, nous arriverons à une solution satisfaisante.

# Récupération des informations "cachées"

Deux choses restent à extraire:

- Le contenu de l'*EPROM*.

- La combinatoire d'un *PAL* (32 mots de 8 bits) servant à du décodage d'adresses.

## Dump de l'EPROM

Après un (court) instant de frayeur, le PC de Jeff se montrant un peu récalcitrant au démarrage, l'extraction de l'*EPROM* se fait sans difficulté.

Ici, on voit l'*EPROM* montée sur la carte-fille du PC.

![ep1](/images/ep1.jpg)

On lance l'utilitaire, et hop, on observe ceci:

![ep2](/images/ep2.jpg)

Les divers textes apparaissant (SQUALEMON V1.2, ERREUR) sont plutôt rassurants, en ce sens qu'ils semblent indiquer que le dump est correct.

## Analyse du PAL

Bon, là ça se "gâte" dans le sens où le dump de ce type de composant n'est pas pris en charge par le dumper de Jeff.

C'est pas grave, on sort les vieilles recettes, à savoir utiliser le *port parallèle* du PC pour piloter le "bus d'adresse" du *PAL*, et on fait le repérage des valeurs de sortie sur le "bus de données" à l'*oscilloscope*.

![pp](/images/pp.jpg)

Reste à écrire un bout de programme pour piloter le *port parallèle*. Dans quel langage? *Python*? *C*? Non, pas le temps, on y va à l'*assembleur 8088*, à l'ancienne.

Et c'est parti: **Jeff** au pilotage du programme, moi-même au repérage sur la sortie du "bus de données" et au final Jeff notant le résultat.

Vue d'ensemble:

![mh1](/images/mh1.jpg)

Le repérage à l'*oscilloscope*:

![mh2](/images/mh2.jpg)

Et on consigne les résultats:

![mh3](/images/mh3.jpg)

# Conclusion

## Un succès, à peu de choses près

Dans l'ensemble, l'opération (qui était une première pour nous) nous a permis de comprendre mieux la mission difficile du CNAM.

Malheureusement, le temps nous a manqué pour terminer, et il faut bien avouer que nous manquions de préparation (la grève des contrôleurs aériens ne nous a pas aidé en ce sens).

Cependant, nous avons récupéré déjà de quoi largement avancer dans la préservation "logique" de ce micro-ordinateur, et à peu de choses près, nous avons de quoi créer un *émulateur* de celui-ci.

Le compte-rendu de **Jeff** se trouve [ici](http://forum.system-cfg.com/viewtopic.php?f=24&t=1874&start=165#p101912).

## De nouvelles pistes

**Ariane** nous a donné son accord pour une deuxième intervention qui nous permettrait de finaliser ce travail. Elle devrait avoir lieu en *Septembre 2015*.

Forts de cette nouvelle expérience, nous serons en mesure de mieux nous équiper et de mieux nous préparer,
afin que les objectifs et contraintes du CNAM liés à la conservation, ainsi que les dilemmes qui font leur quotidien (doit-on privilégier la sauvegarde du logiciel, au risque d'abimer le matériel ?) soient traîtés au mieux.

Suite à cette intervention, **Olivier** m'a contacté, et devrait nous aider à recueillir plus d'éléments, comme la *disquette* contenant le *BASIC*, la *cartouche Minitel*, ainsi que certains contacts, afin de traiter le problème de la propriété intellectuelle de ces différents logiciels, et des ayants-droit.

## Remerciements

Je tiens à saluer et remercier:

- Le **CNAM** et notamment **Ariane** pour nous avoir autorisé et aidé à étudier cette machine.

- **Olivier** pour les informations collectées.

- **Jeff** pour avoir participé grandement à l'intervention.

- **Yun** pour son soutien moral et sa patience. :)

- Les passionnés de [Silicium.org](http://www.silicium.org/), [MO5.com](http://www.mo5.com/) et [System.cfg](http://www.system-cfg.com/).
