# Fractals... et survie

Le programme que nous vous présentons mermet de créer des cartes à l'image de celles que l'on trouve dans les atlas, et de les observer en perspective cavalière avec les courbes de niveau ou un ombrage dû à une source de lumière ponctuelle ou encore en suivant le graphisme dit en « fil de fer ».

Le programme vous propose par ailleurs un jeu de survie basé sur le principe de la déduction.

---

• le jeu :

• joueur : en solitaire

• **principe :** votre avion s'est écrasé dans la montagne. Vous n'avez qu'une carte de la région et, seul appareil rescapé de la catastrophe, un altimètre ! La carte indique l'emplacement d'une cabane de trappeurs. Votre but est de vous y rendre...

• **la partie :** la carte indique chaque niveau par un couleur ou un contraste.

Le tour de jeu consiste à vous déplacer en tapant l'initial de l'un des points cardinaux (N, E, S ou O). Le programme vous répond en affichant une altitude comprise entre 100 et 1600 mètres. A vous de vous débrouiller pour atteindre la cabane.

Au départ, votre personnage dispose de 100 points de vie. Il en épuise 1 par déplacement. Heureusement, s'il se trouve dans une zone d'altitue inférieure à 500 mètres, il a une chance de trouver de l'eau (15% de chance). Si c'est le cas, ses points de vie remontent à 100. Pour vous habituer, vous commencerez par jouer avec la trajectoire de votre personnage. Puis, une fois que vous aurez le jeu bien en main, vous supprimerez les lignes comportant un REM LIGNE A SUPPRIMER. Dès lors, vous serez vraiment seul sur les reliefs fractals...

• **le programme :** il met à votre portée l'un des thèmes les plus étranges de la géométrie : les fractals (de *fractus*, brisé, fragmenté).

La théorie, à laquelle sont associés les noms des célèbres mathématiciens Cantor, Dedekind ou Poincaré, n'a pris son essor qu'au début des années 80, grâce au mathématicien français Benoît Mendelbrot. Dire qu'un fractal est la reproduction d'un même motif (carré, triangle, ligne brisée) à une échelle de plus en plus petite sur le motif lui-même est un manière bien "froide" de décrire le phénomène. Et pourtant n'est-ce pas ce qui fait le cristal de neige !

En regardant tourner le programme fractal conçu par Didier Bouchon, auteur de l'_Arche du capitaine Blood_ pour _Ere Informatique_ (voir J&S n°41, « Où vont les jeux micro ? »), on s'aperçoit que le motif de base est la pyramide.

En effet, après avoir affiché quatre points, formant les sommets d'un carré, le programme affiche un cinquième point, à la verticale du centre du carré, mais pas à la même hauteur.

Nous sommes bien en présence d'une pyramide.

L'empilage de pyramides de plus en plus petites n'a jamais dessiné une montagne ! Mais simplement une grande pyramide composée à l'infini de pyramides de plus en plus petites...

Pour introduire le réalisme, il faut insérer des « défauts ». C'est ici le cas. En informatique, pour programmer des « défauts », on aura recours à un tirage aléatoire. Le réalisme exige cependant que les défauts soient contenus dans des limites. Ici, le cinquième point, qui figure le sommet de la pyramide, est calculé à partir de la moyenne des quatre point formant les sommets de la base, à laquelle s'ajoute une valeur d'intensité de la déviation. La grandeur de la déviation, autrement dit du « défaut », diminue proportionnellement à la surface de base. Plus la base est petite, plus la variation de hauteur du sommet de la pyramide est petit. Sans quoi, la surface créée serait hérissée de pics.

Cette fois-ci, l'empilement de pyramides irrégulières donne à l'ensemble l'apparence d'une montagne ou du moins d'un relief respectant les courbes de niveau comparables à celles de la réalité qui nous environne. Si tout hasard avait été exclu, le programme afficherait toujours...une immense pyramide. Le hasard contrôlé appliqué à un fractal crée le relief.

De plus, le programme est paramétrable. Il vous demande la « taille de la maille », la « hauteur de basse », la valeur de la « déviation « et une graine aléatoire. Avec les mêmes données, le programme crée les mêmes surfaces.

## Conseils de programmation

Le listing proposé tourne directement sur Amstrad CPC 6128. Les possesseurs de cette machine n'auront aucune modification à lui apporter. Les possesseurs d'Amstrad CPC 464 et 664 devront réduire un peu la taille de l'image affichée (pour réduire la place prise en mémoire vive). Au-lieu de taper DIM H(128,128), ils remplaceront la valeur 128 par 64 ou 32.

Les possesseurs d'autres machines procéderont de même pour réduire la prise de cases mémoire. Ils rencontreront d'autres problèmes d'adaptation : le Basic et l'affichage. Pour ce qui est de l'adaptation de langage, une table a été conçue pour traduire les mots de Basic. De plus, dans certains cas, certaines lignes de programme comportent un REM Note... .

En rencontrant REM Note 5, le lecteur se reportera à la note 5 pour comprendre comment il doit programmer. Par exemple, s'il peut ou non se dispenser de taper la ligne en question ou par quoi il y a lieu de la remplacer.

• **Problèmes graphiques :** tous les micros ne permettent pas l'usage simultané de seize couleurs ! Il faudra faire en sorte de modifier la valeur de la variable C (désignant un couleur) par une valeur correspondant à votre micro. Si vous ne disposez que de cinq couleurs, il suffira de diviser par 3 la valeur initiale de C et de ne garder que la partie entière du quotient. C'est une méthode. Il y en a d'autres.

**Note 1.** La ligne 10 signifie, dans le langage de l'Amstrad, que toutes les variables seront entières: A, B, C et E à Y et donc à l'exclusion de D et de Z. Il s'agit donc de l'équivalent de % placé derrière un nom de variable, par exemple A% signifie dans de nombreux Basic que la variable A est entière. Les uitlisateurs qui ne possèdent ni le DEFINT ni le % utiliseront pour toutes les variables le mot de Basic INT. La valeur finale d'une variable A devra être A = INT(A). C'est-à-dire « partie entière de A », à l'exclusion des décimales.

**Note 2.** Très important ! Il s'agit du « dimensionnement des variables indicées ». Il se peut que votre micro ne supporte pas les valeurs mises entre parenthèses. Essayez de trouver des valeurs les plus élevées possibles. Par exemple H(100,100). Ces valeurs conditionnent la taille de la carte que vous pourrez afficher à l'écran.

**Note 3.** Ligne à supprimer (sauf pour Amstrad). Elle indique qu'on choisit une définition moyenne, que l'on place la couleur 18 dans le « godet "numéro 1. Le pinceau 1 (PEN 1) peindra en couleur 18.

**Note 4.** Le WHILE-WEND est un test du type « tant que ... alors recommence ». La ligne 150 signifie simplement "tant qu'une touche n'a pas été frappée, retourne à la ligne 150. Bref « attends « ! On peut taper `GET A$` ou $150 A$=INKEY$: IF A$="" THEN 150`.

**Note 5.** La ligne 160 propose deux GOTO adressés différement, en 40 ou en 1380. EN mode GOTO 40 (tel que le listing est présenté), vous pourrez créer des cartes, mais pas jouer. En mode 1380, vous pourrez jouer sur une carte coloriée vue en plan, mais sans pouvoir accéder aux autres types de vue. Nous vous conseillons de sauvegarder deux fois votre programme lorsque vous l'aurez tapé. L'une avec GOTO 40 ; l'autre, avec GOTO 1380. Cette procédure, pour archaïque qu'elle puisse paraître, permet de gagner de la place.

**Note 6.** La ligne peut être supprimée sur les machines ne disposant pas de cette instruction.

**Note 7.** Cette ligne comporte un PLOT, c'est-à-dire un ordre d'affichage graphique. Il est toujours suivi des coordonnées en X et en Y désignant le point qui doit s'allumer. Il est de plus suivi de C qui désigne la couleur d'affichage. Attention ! Si C était supérieur au nombre de couleur dont voud disposez, le programme s'arrêterait tout net. La valeur de C peut être modifiée à la ligne précédente, en 330. Pour réduire C, il suffit de multiplier la variable N par une valeur de votre choix et de fixer une limite à C. Par exemple, IF C supérieur à 5 alors C=5. Au PLOT X,Y,C on peut toujours substituer un ordre désignat d'abord la couleur, type COLOR=C, puis la position du point PLOT X,Y.

**Note 8.** Cette note est indiquée en ligne 370 et 680. C'est le WHILE-WEND. Il peut aisément être transformé en 370 REM et 680 IF P < = 1 THEN GOTO 380.

**Note 9.** Le AND &FFFE n'est pas indispensable, même pour les possesseurs d'*Amstrad*. Pour les autres machines, il n'est pas question de l'utiliser. Il a pour objet de rendre pair un bit particulier.

## Les variables remarquables

Tout le programme est construit pour donner une valeur cohérente à la troisième dimension, celle qui donne le volume ! Les deux variables de base sont donc X, Y. La valeur Z qui désigne la troisième dimension est ici appelée H(X,Y). C'est la « Hauteur » au point de coordonnées X,Y.

### Mise en route du programme

Cinq valeurs doivent être indiquées après avoir choisi l'option « nouvelle surface » :

- la maille, une valeur de0 à 3 bornes inclues ;
- la hauteur de base. Tapez une valeur comprise entre 10 et 60. Il s'agit de l'altitude minimale sur la carte ;
- la déviation. Elle doit être inférieure ou égale au « pas », pour ne pas produire des reliefs irréalistes. Cela dit, que rien ne vous empêche d'esayer des valeurs supérieures ;
- la graine est une valeur quelconque ;
- la taille. C'est celle de l'image. Cela dépend de la taille mémoire de votre micro. La valeur doit être une puissance de deux (32, 64, 128).
