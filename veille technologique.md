Cette veille technologique portera sur les nouveautés de l’update 2019.1 de PhpStorm
====================================================================================

1 debogage
-----------

Avec PhpStorm et Xdebug on peut maintenant effectuer un débogage étape par étape dans les fichiers .twig 
et .blade.php d'origine (non compilés). Tous les avantages du débogage sont disponibles: voir le contexte,
les variables locales et globales, ajouter des surveillances, s'exécuter étape par étape,…

2 le code mort
---------------

PhpStorm peut maintenant détecter le code redondant et met en évidence les classes,
les membres de la classe et les fonctions qui ne sont jamais utilisées. L'inspection de déclaration non utilisée
prend en compte les utilisations dynamiques du code, par exemple via des méthodes magiques.
Pour vérifier le rapport pour l'ensemble du projet, il faut sélectionner « Code -> Inspecter le code…. »

3 outils 
--------

On peut maintenant convertir la concaténation de chaînes en interpolation,
convertir une concaténation ou une interpolation en appel sprintf,
copier une chaîne concaténée dans le Presse-papiers et effectuer bien d'autres tâches. Appuyez sur Alt + Entrée
sur une chaîne pour voir les actions disponibles.

4 Supprimer les variables non utilisée
--------------------------------------

PhpStorm 2019.1 introduit un nouveau correctif rapide qui aide à se débarrasser des variables inutilisées
apparaissant dans les listes d’utilisation des assignations ou des fermetures.
Le correctif rapide est suffisamment intelligent pour détecter les situations où l'expression d'affectation
peut avoir des effets secondaires

5 réusinage
-----------

Avec la nouvelle refactorisation déplacer vers la classe,
nous pouvons transférer des fonctions ou des constantes à la classe à laquelle elles appartiennent logiquement.
PhpStorm trouvera et modifiera toutes les utilisations pour nous. Nous pourrons donc déplacer plusieurs fonctions
simultanément en les sélectionnant dans la fenêtre de l'outil Structure.

6 La méthode peut être une inspection «statique»
-------------------------------------------------

Si une classe a une méthode qui n’utilise aucune référence d’instance,
PhpStorm la détectera et lui proposera une solution rapide: il faudra appuyer sur Alt + Entrée pour la méthode
et la rendre statique. Toutes les utilisations seront mises à jour automatiquement.

7 Docker
--------

Pour les interprètes basés sur Docker Compose, nous pourrons désormais choisir entre exécuter en mode docker
ou exécuter en mode docker pour exécuter des conteneurs. Si on ne souhaite pas redémarrer un conteneur
lourd à chaque exécution de test, on peut  le réutiliser en sélectionnant l'option docker-compose exec. 
Nous pourrons également utiliser la commande docker-composition pour les conteneurs légers ou ceux ne
fonctionnant pas en mode démon (c’est-à-dire en s’arrêtant juste après leur démarrage).

PHP :
=====

8 Auto complétion
------------------

À l'aide d'un fichier spécial, .phpstorm.meta.php, PhpStorm est maintenant capable de suggérer des arguments
et de mieux renvoyer des valeurs. Cela couvre les situations où, au lieu d'un type simple comme un entier
ou une chaîne, nous pourrons voir un certain ensemble de constantes suggéré. Ou si on s’attend à ce que
certaines fonctions renvoient une certaine constante.
Nous pourrons également améliorer les suggestions dans PhpStorm pour notre bibliothèque ou notre projet
en fournissant notre propre fichier .phpstorm.meta.php.

9 imports
---------

Ils ont également  retravaillé les actions d’inspection et d’intention liées aux espaces-noms important
et utilisant FQN. L'idée principale derrière eux est d'éviter autant que possible les qualificatifs.
Maintenant, PhpStorm nous permettra simplement de supprimer si possible un qualificatif redondant,
ou de le remplacer par la déclaration d'importation ‘use’ correspondante. De même, lorsqu’on colle du code
dans un fichier, PhpStorm nous demandera de réutiliser un alias existant.

10 Nettoyage de code 
--------------------

Dans PhpStorm 2019.1, l’outil Code Cleanup est livré avec des intentions spécifiques à PHP: il peut optimiser
les occurrences de noms de classe complets en ajoutant l’instruction ‘use’ ou en supprimant la partie inutile.
Il peut également résoudre automatiquement les problèmes de style de code avec PHP CS Fixer ou phpcbf de
PHP_CodeSniffer. Exécuter un nettoyage avant la validation de VCS ou le déclencher manuellement à tout moment via
__Code -> Code Cleanup…__ .

Technologies du Web :
=====================

11 Documents mis à jour et compatibilité du navigateur
------------------------------------------------------

La documentation (F1) relative aux propriétés CSS, aux balises et attributs HTML contient désormais des
descriptions et des informations à jour sur la prise en charge du navigateur par MDN, ainsi que des liens
vers les articles complets sur MDN. En outre, pour vérifier que toutes les propriétés CSS que nous utilisons
sont prises en charge dans la version du navigateur cible, nous pourrons activer une nouvelle inspection
de la compatibilité du navigateur dans les préférences.

12 Prise en charge améliorée de TypeScript dans les applications Vue
--------------------------------------------------------------------

PhpStorm exploite maintenant le service de langage TypeScript avec son propre support TypeScript pour
le code TypeScript dans les fichiers .vue. Cela signifie que l’on obtiendra désormais une vérification de type
et des informations de type plus précises, on pourra utiliser les solutions rapides fournies par le service
et consulter toutes les erreurs TypeScript dans le fichier en cours dans la fenêtre de l'outil TypeScript.

13 Nouvelles inspections pour les applications angulaires
---------------------------------------------------------

Pour les applications angulaires, PhpStorm ajoute 17 nouvelles inspections qui nous aideront à détecter
les erreurs spécifiques à Angular dans nos applications lors de la frappe et à proposer des solutions rapides.
Travaillant à la fois dans les fichiers TypeScript et modèles, ces inspections vérifieront notre utilisation
des liaisons, des directives, des composants et de nombreux autres éléments.

14 nouvelle console de débuggeur 
--------------------------------

Découvrez la nouvelle console de débogueur interactive améliorée dans les fenêtres de l’outil de débogage
JavaScript et Node.js! Il affiche désormais les objets à l'aide d'une vue arborescente et prend en charge
le style des messages de journal avec CSS et leur regroupement à l'aide de _console.group ()__
et __console.groupEnd ()__. Nous pourrons également filtrer tout type de messages de journal.

15 convertir des functions avec Promise vers async/await
--------------------------------------------------------

nous pourrons modifier automatiquement une fonction qui renvoie une promesse avec des appels __.then ()
et .catch ()__ à une fonction asynchrone utilisant la syntaxe async / wait. Nous devrons  simplement appuyer
sur __Alt-Entrée__ sur le nom de la fonction et sélectionnez Convertir en fonction asynchrone.
Cela est possible non seulement dans les fichiers TypeScript, mais également dans JavaScript et Flow.

IDE
===

16 Popups
----------

Dans cette nouvelle fenêtre de navigation, nous trouverons les points de code récemment visités,
présentés avec un contexte - quelques lignes avant et deux lignes après. Tous les emplacements sont classés
par ordre chronologique dans cette fenêtre contextuelle, avec le dernier emplacement visité en haut.
Pour appeler le nouveau menu contextuel Lieux récents,nous devrons  appuyer sur les touches
__Cmd-Maj-E / Ctrl + Maj + E__. Taper n'importe quel texte à rechercher dans le contexte.

17 Améliorations du VCS
-----------------------

Une nouvelle case à cocher «Désactiver tout» pour les validations Git partielles nous  permettra de désélectionner
tous les fragments de code en même temps, puis de choisir ceux que l’on souhaite valider. De plus, les actions
de réparation, de squash et de choix de recherche sont maintenant disponibles dans le journal Git.

18 Thèmes d'interface utilisateur personnalisés
-----------------------------------------------

Si les thèmes blanc et Darcula par défaut ne nous suffisent pas, nous pourrons  en créer  un personnalisé!
La couleur de tout élément de votre IDE, des icônes aux boutons radio en passant par les flèches,
est maintenant configurable. Réglez tout à votre guise et sauvegardez-le dans un nouveau plugin de thème!

19 Outils de base de données
----------------------------

Les outils de base de données dans PhpStorm ont été améliorés grâce à nos collègues de l'équipe DataGrip:
*Prise en charge de nouvelles bases de données: Greenplum, Vertica et Apache Hive
*La complétion de code prend en charge les instructions combinées pour CREATE et DROP
*Prise en charge des attributs DEFINER dans MySQL et MariaDB
*Prise en charge du mode Oracle dans MariaDB
*Nous pourrons maintenant définir le dossier par défaut pour un projet
