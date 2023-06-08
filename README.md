<h1 align="center">Fortunes-FR</h1>

# ENGLISH INFORMATION

This package contains French Fortunes for GNU/Linux. They are all in French 
languages, so this package is interesting for people who know French language.

Therefore, any further information will be provided in French. However, please
note that an English version of the license is provided in the file COPYING. 
For installation instructions, please see the INSTALL file.

## QU'EST CE QUE C'EST ?

Le programme fortune, disponible sous GNU/Linux mais qui provient à l'origine 
du monde BSD, permet d'afficher aléatoirement des citations.

fortunes-fr est une base de donnée pour le programme fortune, qui regroupe 
plus de 2100 citations en français dans des domaines variés allant de la 
littérature au cinéma, de l'humour à la politique... Un exemple ?

<h4 align="center">Ton bras est invaincu, mais non invincible. -+- Pierre Corneille, Le Cid -+-</h4>

Les citations sont réparties dans différents fichiers, qui correspondent
chacun à une catégorie. Il est donc possible d'afficher uniquement certaines 
catégories de citations, et ainsi de s'adapter aux goûts de chacuns. Voici ces 
différentes catégories:

  * bd                    : Extraits de bande dessinées
  * cinema                : Citations extraites du monde du cinéma
  * droit                 : Extraits de textes de loi
  * fr.rec.photo          : Citations extraites du newsgroup fr.rec.photo
  * GDP                   : Guide du Debianiste Pervers : citations issues de
                            debian-french, debian-devel-french et 
                            debian-user-french
  * haiku                 : Haïkus (forme poétique japonaise)
  * humoristes            : Citations d'humoristes
  * humour                : Blagues, devinettes, jeux de mots, perles, etc.
  * informatique          : Citations en rapport avec l'informatique
  * litterature_etrangere : Extraits d'oeuvres littéraires étrangères
  * litterature_francaise : Extraits d'oeuvres littéraires françaises
  * mysoginie             : Citations mysogines
  * personnalites         : Citation de personnes connues, principalement
                            du show business
  * philosophie           : Pensées philosophiques ou citations de 
                            philosophes
  * politique             : Citations d'hommes politiques
  * proverbes             : Proverbes et dictons d'origine diverse
  * religion              : Extraits de livres religieux, ou citations se
                            rapportant à la religion
  * sciences              : Théorèmes, lois, citations de scientifiques

Ce recueil ne demande qu'à être agrandi, aussi si vous avez des citations que 
vous aimeriez voir figurer dans cette compilation, et si vous êtes en accord 
avec la licence contenue dans le fichier COPYING, n'hésitez pas, envoyez moi 
un mail (aurelien@aurel32.net). De même, si vous constatez des erreurs ou des 
imperfections, n'hésitez pas à me contacter.


## UTILISATION DE FORTUNES-FR

Avant d'utiliser fortunes-fr, il faut tout d'abord l'installer. Pour celà, se
reporter au fichier INSTALL.

Une fois l'installation effectuée, il suffit d'executer le programme fortune 
pour voir apparaître une citation :

```bash
$ fortune
```

<h4 align="center">Les logiciels, c'est comme le sexe ; C'est meilleur quand c'est libre. -+- Linus Torvalds -+- </h4>

Cette citation provient du fichier informatique. Lorsque aucun fichier n'est 
spécifié, la citation est choisie au hasard parmi tous les fichiers (en tenant 
compte de leurs poids respectifs). Si au contraire on souhaite choisir une 
citation d'un fichier spécifique, il est possible de le spécifier :

```bash
$ fortune droit
```

<h4 align="center">Les hommes naissent et demeurent libres et égaux en droits. Les distinctions sociales ne peuvent être fondées que sur l'utilité commune. -+- Déclaration des droits de l'homme et du citoyen (26 août 1789) - Article I -+- </h4>

La liste de toutes les fichiers s'obtient avec l'option -f. Il est également 
indiqué l'origine des fichiers et leur poids relatif de citations :

```bash
$ fortune -f
```

100,00% fr
    10,02% sciences
     3,89% religion
     1,97% proverbes
     2,11% politique
     6,98% philosophie
     1,69% personnalites
     1,03% mysoginie
    38,90% litterature_francaise
     4,96% litterature_etrangere
     1,08% informatique
     0,75% haiku
     1,17% GDP
     5,29% fr.rec.photo
     2,90% humour
     6,84% humoristes
     1,26% droit
     5,99% cinema
     3,18% bd

Pour ceux qui veulent aller plus loin, la page man fortune(1) est d'une grande
aide.

## RAJOUTER DES CITATIONS

Par défaut, le programme fortune va chercher ses fichiers de citation à partir 
des répertoires `/usr/local/share/games/fortune` ou `/usr/share/games/fortunes`. 
Chaque groupe de citations est composé de deux fichiers, le fichier source 
(qui contient les citations), et le fichier de données (qui contient la 
longueur et la position des citations), de même nom que le fichier source avec
l'extension ".dat". Par exemple, si "litterature" est un fichier de citations, 
alors "litterature.dat" est le fichier de données qui le décrit. La page de 
man strfile(8) vous un peu plus sur l'utilité de ces fichiers.

Le séparateur de citation doit être le caractère %, précédé et suivi d'un 
retour à la ligne. Ne pas oublier de terminer la dernière citation par le même 
caractère %, sinon celle-ci ne sera pas prise en compte.

Pour rajouter des citations, il faut donc éditer le fichier source, puis 
mettre à jour le fichier de données à l'aide du programme strfile.

## FORMATAGE DES CITATIONS

Cette partie décrit le format des citations dans la base de données, afin
de rendre plus facile sa maintenance, mais ce ne sont pas des règles 
absolues :

 - Aucune citation ne doit dépasser 72 caractères par ligne, ceci afin que la 
   citation s'affiche toujours correctement, qu'elle soit utilisée en 
   signature de mail, ou simplement affichée à l'écran. 

 - Dans la mesure du possible, le nom de l'auteur de la citation doit être
   indiqué. Il doit être placé juste après la citation, et doit être placé
   entre deux séquences "-+-", le tout précédé par une tabulation. 
   Par exemple :
   
	-+- Voltaire -+-

   Dans le cas où cette ligne dépasse 72 caractère, il faut aussi préceder la
   seconde ligne d'une tabulation, et aligner les permières lettres.
  
 - Si le nom de l'oeuvre est connu, il peut alors être précisé après le nom
   de l'auteur, séparé par une virgule. Par exemple :

	-+- Voltaire, Dictionnaire philosophique -+-

 
