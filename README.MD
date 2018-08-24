# JPL Projet de Rover Open Source
Le Rover Open Source JPL est une version modèle réduit open source, à monter soi même du rover à 6 roues que le JPL utilise pour explorer la surface de Mars. Le Rover Open Source est conçu quasiment uniquement depuis des éléments disponibles dans des magasins accessibles au grand public. Ce projet est pensé pour être une expérience d'enseignement et d'apprentissage pour ceux qui souhaitent pratiquer de l'ingénierie mécanique, logicielle, éléctronique, ou robotique.

<img src="images/rover.png" width="100%">
<p><img src="images/rover-silver.png" width="43%"/><img src="images/rover-climbing.jpg" width="57%"/></p>

## A propos du projet

### Motivation
Le JPL cherche toujours à inspirer la prochaine génération de scientifiques, ingénieurs, et roboticiens pour nous aider à explorer notre système solaire (et au dela!). Nous publions les plans pour ce rover comme une tentative de donner à ces jeunes enthousiastes un projet robotique amusant qui leur apprendra la robotique et de la pratiquer tôt et à un cout moindre.

### Specifications & Attributs Techniques

Les attributs spécifiques du robot que vous assemblerez va quelque peu dépendre du type d'éléctronique et des moteurs que vous achèterez pour le système. Les nombres ci-dessous correspondent à la version qui contient exactement les éléments que nous suggérons dans nos documents d'assemblage et liste d'éléments. Ci-dessous, vous pouvez voir quelles parties pourraient êtres changées pour quelles versions.


| Attribut	                                    | Valeur [imperial]        | Valeur [SI]            |
| ----------                                    |:-----:                   | :-------------:        |
| Poids                                         | 25 [lbs]                 | 11.34[kg]              |
| Empreinte                                     | 24x14 [in]               | 60.96x30.48 [cm]       |
| Capacité de la batterie                       | 5200 [mAh]               | 5200 [mAh]             |
| Taux de déchargement de la batterie           | 8 [A]                    | 8 [A]                  |
| Consommation de courant nominale              | 1.2 [A]                  | 1.2 [A]                |
| Temps de fonctionnement                       | 5 [hrs] (continual use)  | 5 [hrs] (continual use)|
| Vitesse Max                                   | 6.7 [in/s]               | 17.018 [cm/s]          |
| Montée maximale à 90°(1)                      | 12 [in]                  | 30.48 [cm]             | 
| Différence de hauteur maximum entre les côtés | 14 [in]                  | 35.56 [cm]             |
| Communication (dans ce guide)                 | App Bluetooth(Android uniquement) et Manette Xbox||
| Coût                                          | < $2,500                 |                        |

A nouveau, les statistiques ci dessus dépendent de quel composants vous choisissez en achetant les éléments. Une modification possible est celle des moteurs; vous pouvez, par exemple, choisir des moteurs avec des TPM plus élevés (pour faire aller le rover plus vite) en sacrifiant le couple maximal de calage (1), ce qui limitera potentiellement la capacité du rover à gravir des obstacles. Une selection de moteurs qui s'intègreront facilement avec le reste du rover peut être trouvée à [Feuille de séléction des moteurs](https://www.pololu.com/category/115/25d-mm-metal-gearmotors), ou n'importe lequel des moteurs 12V fonctionnerait facilement dans le robot. Notez, toutefois, qu'il est important de prendre en compte la consommation de courant et d'être certain que toute l'éléctronique et la batterie peuvent fournir la puissance requise pour n'importe quelle modification faite aux moteurs.

### Fonctionnalitée
Ce rover est conçu pour fonctionner de manière similaire au rover 6 roues sur Mars et utilise quelques uns des mécanismes majeurs utilisés sur Mars pour traverser les surfaces rocheuses:
 * __Rocker-Bogie:__ Le système de suspension Rocker-Bogie permet aux 6 roues d'être en contact permanent avec le sol lors du franchissement d'obstacles.
 * __Pivot Différentiel:__ Permet au poids d'être mécaniquement déchargé d'un côté du rover à l'autre pendant le franchissement.
 * __Ackerman Steering 6 roues:__ Mécanisme de conduite et manoeuvre/direction qui contrôle les roues et à quelle vitesse chacune d'elle tourne.

Nous avons choisi un Raspberry Pi pour être le "cerveau" de ce rover à cause de sa versatilité, accessibilité, simplicité, et la possibilité d'ajouter et améliorer vos propres modifications. N'importe quelle méthode vous permettant de connecter avec un Raspberry Pi (bluetooth, WiFi, Appareils USB, etc) peut être interfacé avec le système de contrôle du robot.

![Rover communication](images/communication.png)

De plus, voici les ports de communications ouverts et matériels sur le Raspberry Pi:
 * 4 ports USB (3 si une manette Xbox est utilisée)
 * Port caméra du Raspberry Pi
 * 1 I2C Bus (0 en cas d'utilisation de l'écran à matrice LED)
 * 2 SPI Bus (1 en cas d'utilisation de l'écran à matrice LED)
 * 3.5mm Jack Audio
 * 13 GPIO pins (6 en cas d'utilisation de l'écran à matrice LED)

En utilisant ces ports, vous pourriez théoriquement conduire le rover de manière autonome depuis la caméra, depuis un dongle USB relié à n'importe quoi (votre propre manette de jeu, un micro USB, ou pleins d'autres choses... soyez créatifs!), ou depuis n'importe quelle interface utilisants les ports GPIO du Raspberry Pi (Détecteurs de distance, accéléromètres, et bien plus). Nous vous avons uniquement donné deux façon simple de contrôler le rover pour commencer... Nous voulons que vous trouviez encore plus de solutions!

Pour le système d'alimentation du rover, il reste aussi suffisamment de puissance qui peut être utilisée pour vos propres ajouts et améliorations. Voyez la [Documentation du sous sytème éléctrique](Electrical/) pour plus de détails.

### Autres ressources
En plus de ce dépôt qui contient toute la documentation pour ce projet, il y'a deux sites internet supplémentaires liés à ce projet. L'un est une simple page qui contient les informations générales et un aperçu du rover et de son fonctionnement:

https://opensourcerover.jpl.nasa.gov

Il y'a également un forum géré par les utilisateurs pour aider à la communication autour de ce projet. **__Note: JPL et Caltech n'ont pas de liens officiels avec ce forum; il est géré par des individus tiers.__** Sur ce forum, vous pouvez poser des questions si vous avez besoin d'aide ou de clarifications sur des aspects du projet. De plus, vous pouvez poster et promouvoir n'importe quelles modifications ou ajouts que vous avez créé pour ce projet. Nous encourageons vivement les ajouts et modifications à être partagées sur le forum pour que ce projet sa communauté puissent grandir.

http://s15.zetaboards.com/JPL_OpenSource_Rover/index/


### Compétences nécéssaires
Ce projet à des éléments d'assemblement/fabrication mécanique, utilise un tas de composants éléctriques, et un logiciel qui le fait fonctionner. Pour pouvoir mener ce projet à bien, vous aurez besoin d'avoir un peu d'expérience dans les choses suivantes:
 * __Fabrication/Machining:__ Même si la plupart des éléments sont disponible facilement, il y'a quelques modifications nécéssaire pour les adapter au projet. Ces modifications sont les suivantes:
   * Découpe de métal en utilisant une scie à ruban/dremel
   * Percer en utilisant une perceuse à colonne/perceuse à main
   * Limer et poncer pour nettoyer les éléments
   * Sécurité général lors de l'utilisation des machines
 * __Electronique:__ Ce projet utilise des composants tels que des moteurs, controlleur de moteurs et des batteries. Il est important d'avoir de l'expérience avec les process suivants:
   * Soudure
   * "Debuggage" electrique
   * Câblage
   * Sécurité Electrique
 * __Logiciel:__ Le cerveau du rover est un Raspberry Pi. Est inclus dans ce dépôt le logiciel prêt à faire fonctionner le rover, mais quelques connaissances sont requises pour avoir tout prêt à fonctionner sur le Raspberry Pi:
   * Connaissance basique de Linux
   * Connaissance basique de Python

La plupart des compétences ci-dessus peuvent être acquises assez rapidement en regardant des vidéos ou en faisant des recherches sur internet, et au travers de ce projet nous essayons de donner des informations sur certaines d'entre elles également. Voyez les documents concernant l'assemblage pour plus d'informations.

### Outils nécéssaires
Ce projet suppose que vous avez déjà certains outils standard pour aider à l'assembler. Si vous n'avez aucun des outils optionnels, nous fournissons des exemples de services en ligne que vous pouvez utiliser pour vous faire fabriquer et envoyer ces elements.

#### Outils obligatoires
 * Jeu de clés allen SAE
 * Jeu de clés SAE
 * Pince(pas de précision, au vu de la liste ci-dessous je suppose pince plate)
 * Pince coupante
 * Pince à dénuder
 * Fer à souder
 * Etain
 * Multimètre digital
 * Perceuse à main ou perceuse à colonne
 * Dremel, Scie à ruban ou scie à main
 * Objets pour interagir avec le Raspberry Pi (Clavier, souris, moniteur, Transfo micro USB 5V)

#### Outils optionnels
 * Imprimante 3D
 * Découpeur Laser
 * Alimentation (Pour tester sans utiliser de batterie)

### Temps requis attendu
D'après notre expérience, ce projet ne prends pas moins de 200 heures-personne à assembler, et peut être bien supérieur suivant la familiarité et le niveau de compétence des personnes impliquées. Des assembleurs expérimentés peuvent être capable de monter ce projet dans ce laps de temps. Toutefois, ce projet est vu comme un outil d'enseignement et d'apprentissage. Au travers de la documentation, nous essayons de donner des informations supplémentaires pour ceux qui n'auraient jamais tenté ce genre de projet.


# Décharge
**La référence spécifique ici à n'importe quel produit commercial, process, service par appellation de nom, marque déposé, manufactureur ou autre ne constitue ni n'implique son approbation par le Gouvernement des Etats Unis ou le Jet Propulsion Laboratory(JPL), California Insitute of Technology(CalTech). Government sponsorship acknowledged.** 

**En téléchargant, clonant, ou d'une quelconque manière utilisant le contenu de ce dépôt, vous acceptez les termes spécifiés dans le DISCLAIMER.txt file](/DISCLAIMER.txt) joint.**

## Débuter

### Organisation des dossiers
![Rover build roadmap](images/folders.PNG)
Le dossier principal /osr/ contient toute la documentation et les informations nécéssaires pour ce projet, divisé en 3 parties principales: Mécanique, Electrique, et Logiciel. Chacune de ces sections est conçue pour être relativement distincte des autres et devrait être facilement prallelisable, signifiant qu'elles pourraient être exécutées de manière simultanées par différents groupes. Il y'a un fichier README.md dans chacune des sections pour vous aider à parcourir les informations de cette section

### Commander des pièces

#### Liste des éléments
La [liste maitre des éléments](osr_Master_parts_list.xlsx) contient tout les éléments nécéssaires à l'assemblage complet du robot tel que listé dans notre documentation. Nous savons que vous pouvez vouloir changer, ajouter, ou refaire certaines sections, donc chaque section invidivuelle d'assemblage contient également une liste des éléments correspondant à la section de ce projet. *Notez que ces listes d'éléments individuelles recommendent d'acheter les quantités nécessaires __uniquement pour cette section__. Soyez surs de comptez la quantité dont vous avez besoin pour les éléments comments (notamment vis, écrous, boulons et autres matériels communs) si vous changez les sous ensembles.*

##### Partage de panier
Pour aider le processus de commande nous avons rassemblé quelques liens d'un grand nombre de ces éléments, si vous souhaitez assembler éxactement ce qui est dans notre documentation d'assemblage.

[McMaster](https://www.mcmaster.com/order/rcvRtedOrd.aspx?ordid=5887891246&lnktyp=txt)

[Amazon](https://www.amazon.com/gp/registry/wishlist/3ELV1FY8J7ZYP/ref=cm_sw_em_r_z_g__wb)

[Pololu](https://www.pololu.com/wishlist/1J10953)

[Adafruit](https://www.adafruit.com/wishlists/460400)

Digikey: 
Le dossier Bill of Materials contient un fichier de liste des matériels pour un magasin spécifique. Nous cherchons un meilleur moyen d'aider avec la partie commande, toutefois pour l'instant la façon la plus simple est de prendre le fichier [Digikey Bill of Materials](Bill%20of%20Materials%20Files/Digikey_BOM.csv) et de l'uploader sur [Digikey](https://www.digikey.com/). Vous trouverez le "BOM Manager" sur leur page d'accueil, commencez une nouvelle BOM, la vous pourrez uploader ce fichier.

#### Impression 3D et découpe laser

En plus de commander tout les éléments de la liste, nous recommandons que certains soient imprimé en 3D et découpées au laser. Si vous n'avez pas accès à une imprimante 3D ou à un découpeur laser, nous avons ajouté des services en ligne ou vous pouvez avoir ces éléments fabriqués et envoyés chez vous. Vous trouverez les instruction dans les fichiers [Body Build Doc](Mechanical/Body%20Assembly/Body%20Build%20Doc.pdf),  [Corner Steering Build Doc](Mechanical/Corner%20Steering/Corner%20Steering%20Build%20Doc.pdf), et [Head Assembly Build Doc](Mechanical/Head%20Assembly/Head%20Assembly%20Build%20Doc.pdf).

#### Planches de circuit imprimés (PCBs)
Il y'a quelques circuis imprimés conçus pour ce projet. Vous pouvez monter ces circuits sur une platine d'expérimentation(planche à pain, breadboard) plutôt que de commander les PCB si vous le désirez (Nous avons inclus les schémas dans la section Eléctrique), mais nous avons inclus les fichiers pour les PCB car cela simplifie grandement l'assemblage. Ces fichiers se trouvent ici [Fichiers PCB](Electrical/PCB%20board%20files%20and%20schematics/Board%20files). Ils peuvent être commandés chez [Osh Park](https://oshpark.com/) en déposant chacun des fichiers .zip.

### Feuille de route de l'assemblage

![Rover build roadmap](images/roadmap.PNG)

Ci dessus est un exemple de feuille de route que vous pouvez utiliser pour assembler le rover et quelles parties de l'assemblage dépendent des autres sections. Elle est séparées en 5 étapes:
 * __Etape 1:__ Rassembler tout les éléments!
 
 * __Etape 2:__ Une fois que vous avez tout les éléments, toutes les parties de l'étape 2 peuvent être complétées en parrallèle. Il est *hautement* recommandé de débuter les tests éléctriques des composants en dehors du robot avant de faire l'installation des parties éléctriques à l'intérieur du corps complet du robot. Vous pouvez aussi travailler sur le logiciel à n'importe quelle étape entre maintenant et la fin.
 
 * __Etape 3:__ Pendant l'étape 3, les sous ensembles mécaniques devraient tous êtres assemblés et être intégrés ensemble. Une partie des tests du système éléctrique devrait déjà être fait, ainsi que des avancées sur le logiciel

 * __Etape 4:__ Le rover est assemblé mécaniquement et tout les sous ensembles intégrés. Pendant l'étape 4, vous commencez l'intégration des composants éléctriques et des divers cables d'alimentation et de données qui parcourent le rover.

 * __Etape 5:__ Une fois l'éléctronique alimentée et communiquante avec le reste des éléments, vous testerez et calibrerez les moteurs dans le système.

 * __Etape 6:__ Une fois que tout est testé et calibré et le logiciel est fonctionnel, le robot est complètement assemblé et fonctionnel!

 * __Etape 7:__ Ajouter vos propres améliorations! Nous avons choisi le Raspberry Pi comme cerveau du projet pour qu'il soit facile d'ajouter, modifier et améliorer des éléments sur ce robot. Quelques idées d'améliorations pour vous aider à réfléchir: un sonar pour détecter les collisions, IMU pour l'orientation / conduite en boucle fermée / cartographie des obstacles, caméra pour l'identification des objets et le pistage, divers senseurs (température, pression, humidité), panneaux solaires, ou même un bras robotique!
 
 ## Joyeux assemblage!!
 Si vous avez des questions ou rencontrez des problème pendant votre assemblage, demandez sur le [forum](http://s15.zetaboards.com/JPL_OpenSource_Rover/index/).

 ## Equipe du projet
 ### Leader du projet:
 Michael Cox
 ### Equipe de développement:
 Eric Junkins et Olivia Lofaro
 ### Remerciements spéciaux à:
 Magdy Bareh, Michelle Viotti, Tom Soderstrom, Dave Gallagher, Jim Rinaldi, Molly Bittner, Christine Fuller, Billy Allen, et Charles Dandino
