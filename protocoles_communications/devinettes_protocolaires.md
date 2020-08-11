# Devinettes protocolaires : une étude sans révélations

Ou comment apprendre sans divulgâchages.

## Introduction

Il existe plusieurs façons d'apprendre, et ma préférée est de refaire une partie, sinon l'ensemble, de la théorie par moi-même.

C'est l'apprentissage sans révélation: il n'y a pas de professeur pour orienter la (re)découverte... ou en gâcher le plaisir.

(je suis d'avis que ce n'est pas très efficace comme façon d'apprendre, mais plutôt amusant)

En exemple: cet essai écrit au fil de mes pensées sur les protocoles de communication. La première partie sera écrite de mémoire de lectures, et la seconde suite à des recherches sur Wikipedia/Internet/Les Livres.

## Première partie

### Protocoles de communication humaine

Loin de moi, pour le moment, l'idée d'en donner une définition formelle. Comment je vois les protocoles de communication pour le moment se résume à ceci: c'est une suite d'instructions constituées d'actions et de réactions permettant à deux entités (ou plus) d'échanger de l'information.

Exemple: la conversation humaine.

Personne A : Bonjour !
Personne B : Bonjour, comment allez-vous ?
Personne A : Magnifiquement, et vous ?
etc.

Lorsque la personne A dit "bonjour", elle communique son intention et son désir d'entreprendre une conversation. La personne B peut refuser de répondre, auquel cas la personne A pourrait répéter son message, ou envoyer un second messsage, contenant par exemple une question ("J'ai dit Bonjour, vous m'entendez?") ou une insulte ("On vous a pas appris à répondre ?"), ou une multitude d'autres messages possibles, du moins en français, sinon en d'autres langues. La personne B peut aussi envoyer le message "Bonjour", qui signifie son intention de répondre, ainsi que son désir de ne pas entamer une discussion. Si la personne B désire en fait commencer une conversation, elle procède comme dans l'exemple, c'est-à-dire qu'elle lance une perche en demandant à la personne A comment va-t-elle. Une conversation peut suivre.

### Protocoles de communication informatique

J'imagine qu'il existe une pléthore de protocoles de communication informatique. Pour le moment, je ne peux nommer que HTTP et TCP/IP, qui sont peut-être la même chose... mais je ne fais pas de distinction exacte. Je ne veux pas me divulgâcher le plaisir de la découverte, alors je refais tout dans ma tête.

Je sais déjà (car j'ai cherché ou que d'autres m'ont donné l'information) qu'il existe un certain nombre de problématiques lorsque deux ordinateurs différents tentent d'échanger de l'information. Liste non-exhaustive:

* l'information peut être interceptée
* l'information peut ne pas être acheminée
* deux informations lancées successivement par l'émetteur peuvent arriver dans l'ordre inverse au récepteur
* il est difficile d'avoir deux ordinateurs avec la même horloge, et donc d'ordonner les messages reçus adéquatemment
* qu'arrive-t-il si les deux ordinateurs parlent en même temps ?

(on voit déjà que j'ai lu sur le sujet, puisque je tente d'utiliser judicieusement la terminologie apprise et certains concepts sur le temps.)

Mais commençons par le début.

Je suis un ordinateur A qui souhaite communiquer à l'ordinateur B une information. Itérons sur le bon protocole.

#### Protocole de communication entre deux ordinateurs, itération 0

Je suis l'ordinateur A, je souhaite envoyer à l'ordinateur B une information - par exemple, une image d'un mignon petit chiot. Par exemple.

Alors je pourrais simplement envoyer l'image.

Erreurs possibles:
* l'ordinateur B est éteint.
* l'ordinateur B n'est pas connecté à un réseau
* l'ordinateur B n'est pas disponible
* l'information a été interceptée 
* l'information a été perdue (panne de courant, par exemple)
* l'information est plus grande que la mémoire disponible de l'ordinateur
* l'information n'est pas retransmise dans son entièreté
* l'information a été corrompue
* autres ?

Une étape à la fois.

##### L'ordinateur B est éteint.

Alors il ne pourra communiquer. Il ne pourra pas dire s'il a reçu l'image, il ne pourra même pas la recevoir. Quelle est la solution pour A ? L'ordinateur A pourrait ré-essayer d'envoyer un certain nombre de fois l'image, à intervalles aléatoires. Et puis abandonner.

L'ordinateur A pourrait aussi envoyer l'information sur un serveur (pour ce contexte, considérons le serveur comme un ordinateur qui ne s'éteint jamais), sur lequel il existe une boître aux lettres destinée à l'ordinateur B. B pourra ainsi récupérer le courrier à la prochaine visite sur le serveur.

Le serveur pourrait être remplacé par un ensemble d'ordinateurs, en se disant qu'au moins un de ces ordinateurs sera ouvert au moment où ordinateur B souhaite récupérer le courrier.

Y a-t-il d'autres solutions pratiques ?

... réfléchissons.

Par pratique, je veux dire des solutions viables.

Exemple non-viable: ordinateur A pourrait décider d'envoyer constamment l'image du petit chiot, tant qu'il n'a pas reçu une confirmation de réception de l'ordinateur B. Ce protocole nécessiterait beaucoup d'activités de la part de l'ordinateur A... et potentiellement que l'ordinateur B est simplement brisé et irréparable, donc toujours éteint. Dans ce cas, l'ordinateur A roulera à l'infini, ce qui n'est pas désirable.

Par contre, cet exemple non-viable nous a permis d'introduire une notion importante: la *confirmation de réception.*

##### L'ordinateur B n'est pas connecté à un réseau

Ici, on pré-suppose avoir défini ce qu'est un réseau. En fait ceci aurait dû être notre premier exemple. Bref.

Je pense que grosso modo les mêmes réflexions qu'en cas d'ordinateur éteint s'appliquent alors, mais je peux me tromper. Dans les deux cas, l'ordinateur A tente de rejoindre l'ordinateur B mais en est incapable. Je reviendrai sur cette section si nécessaire, plus tard. Passons.


