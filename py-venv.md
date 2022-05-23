# Python Venv pour Linux - Tuto vulgaire et incomplet

Le venv est un dossier créé par Python qui contient tous les modules autre que la library standard (ça peut être lourd !), par convention on appelle le venv _"venv"_, mais on pourrait l'appeler _Edmond_, ou _pose-ta-bite-sur-mon-nez_.

Un venv est un bête dossier qui est activé/interprété dans la console de commande qui va exécuter le programme python. Il peut très bien exister plusieurs venv à côté les uns des autres, au final, un seul est utilisé.
Est-ce que ça sert à quelque chose ? Moi je m'en fous, je juge pas.

On peut aussi créer un venv quelque part sur sa machine, avoir le projet ailleurs, et dans une console, on active le venv où qu'il, et... roulez jeunesse ! (Putain, je viens de prendre un coup de vieux sur cette expression...).

T'as rien compris ? C'est normal. Pas à pas :

## Création

Normalement avec Python 3.X.X il n'y a rien de spécial à installer, et ça se passe comme ça (exemples avec des noms différents, ceci créerait donc trois venv pour le prix d'un):

```bash
	python -m venv venv
    python -m venv Edmond
    python -m venv pose-ta-bite-sur-mon-nez
```

## Activation

Ensuite, **TRÈS IMPORTANT** on _active_ l'environnement (sinon ça sert à rien...).
Les IDE peuvent parfois les activer tout seul. Anecdote : dans le cas de VS Code, c'est parfaitement aléatoire... La commande :

```bash
	. /pose-ta-bite-sur-mon-nez/bin/activate
```

Windows :

```shell
	pose-ta-bite-sur-mon-nez\Scripts\activate
```

Si c'est bien activé, dans la console, y a _(pose-ta-bite-sur-mon-nez)_ qui est affiché avant l'invite de commande.

## Usage

### Installer des trucs

D'habitude on utilise pip, mais y a toujours des gens tordus qui vont utiliser autre chose... Pip c'est bien. Les _autres_ sont des cons.
Installons des trucs :

```bash
	pip install untruc
	pip install unautretruc
```

### Voir et enregistrer ce qu'on a dans son venv

Sinon ce serait pas très intéressant...
Donc pour voir ce qu'on a c'est :

```bash
	pip freeze
```

Et on peut enregistrer ça dans un fichier texte avec cette commande native de shell, dans un fichier qu'on appelle généralement _requirements.txt_. On peut aussi lui donner des noms différents, mais le recours à une répétition de blague avec des noms familiers de parties génitales ne serait pas un ressort comique intéressant.

```bash
	pip freeze > requirements.txt
```

### Désactiver le venv

Pourquoi faire ça ? Allez savoir... les gens sont tordus parfois.
Il faut juste taper :

```bash
	deactivate
```

### Recréer un venv

Si un développeur bien intentionné a pensé à mettre un fichier _requirements.txt_, on peut se créer un venv normalement identique ainsi :

```bash
	python -m venv Edmond
	. Edmond/bin/activate
```

Windows :

```shell
	python -m venv Edmond
	Edmond\Scripts\activate
```

Et la nouvelle commande pour tout installer d'un coup (et on fait bien attention que le vens soit **activé** bordel !):

```bash
	pip install -r requirements.txt
```

## Aller plus loin

### Activer un venv hors de son dossier de travail

Ça peut servir si on est un peu à l'étroit en terme d'espace disque. Sinon, franchement, je conseille pas plus de faire ça que de s'enduire les muqueuses de Baume du Tigre. Voilà comment faire (pour le venv, pas pour le baume) :

```bash
	source chemin/vers/dossier-ou-est-le-venv/Edmond/bin/activate
	cd chemin/vers/dossier-du-projet
	python mon-programme.py
```

Windows :

```shell
	call chemin\vers\dossier-ou-est-le-venv\Edmond\Scripts\activate.bat
	cd chemin\vers\dossier-du-projet
	python mon-programme.py
```

### Poetry

Pour ceux qui veulent toujours faire mieux que les autres, être plus malins, avoir la meilleure gomme dans la trousse... [Poetry](https://python-poetry.org/) est une alternative à pip, qui n'est pas (encore ?) intégré nativement dans Python, qui permet de gérer les dépendances de dépendances des modules, ce que ne fait pas pip.
Ouais... mais pip il est sympa quand même, c'est le bon pote qu'on a toujous en soirée, qui fait des bonnes blagues, sans être lourd.

### Des gens qui disent des trucs intéressants sur Python

- [Realpython](https://realpython.com/)
- [Sam & Max](https://sametmax2.com/) (copie : le blog d'origine n'est plus)
