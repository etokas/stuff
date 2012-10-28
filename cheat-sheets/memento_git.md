## Flux de travail (git) ##

### référents GIT ###

**Ces personnes sont dispos pour répondre à toutes vos questions.**

* DTC : Nicolas B
* Shopper : Didier L
* Vidéo : Fred V
* MA : Olivier M

### principes ###

Evitez au maximum les commits sur master (surtout quand plusieurs personnes travaillent sur le même projet). 

La branche master représente la production.

Tous les devs doivent être fait sur une branche partant de master. Une projet peut être recetté sur une branche après avoir mergé le master dedans. 

Les branches se nomment feature-xxx ou hotfix-xxx (xxx peut être un numéro de ticket Mantis dans le cas de la TMA)

### Commandes git ###

Ici sur une feature mais c'est pareil pour un hotfix.

#### créer une branche ####

	git checkout master
	git pull origin master
	git checkout -b feature-super_feature
	git commit …. commit commit 	

#### partage de la branche ####
pour travailler à plusieurs dessus.

	git push -u origin feature-super_feature
	
#### merge de la branche avec master ####
pour voir si l'évolution du master est compatible avec votre dev. A faire régulièrement.

	git checkout feature-super_feature
	git pull
	git merge --stat master
	
#### merge de la branche dans master ####
pour finir le travail

	git checkout master
	git pull
	git merge --no-ff --stat feature-super_feature
	git push

#### supprimer la branche de feature ####
si souhaité 
	
	git branch -d feature-super_feature

#### autres commandes utiles ####

*valable sur la dev m6web*

reverter un commit 

	git revert $numCommit
	
voir un beau log des l'activité du dépot

	git lgg
	
quel c'est t'il passé depuis le dernier pull

	git lc
	
stats sur les modifs à committer

	git diffstat
	
annuler le dernier commit 

	git undo

voir les différences entre deux branches 

	git log feature-super_feature..master
