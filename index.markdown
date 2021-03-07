---
layout: home
---

![alt text](logo-ups.png)

# Traitement de la géométrie : décomposition de maillages en variétés topologiques

# **Contexte** ![](./images/sujet.png)

Ce projet s'inscrit dans le cadre de l'UE Chef d'Oeuvre du Master 2 Informatique Graphique et Analyse d'Images.
Il s'agit d'un projet réalisé tout au long de l'année en petites équipes.

Notre sujet a été proposé par Loïc Barthe et encadré par Nicolas Mellado et concerne la réparation de surfaces non manifold.
En effet, ces surfaces posent de nombreux problèmes en informatique graphique ou en conception assistée par ordinateur.
Nous nous sommes basés sur l'article [Cutting and Stitching : Converting Sets of Polygons to Manifold Surfaces](https://pdfs.semanticscholar.org/f671/0af0fa730aef55a81499cc2f61d73cd364ee.pdf).
Les algorithmes proposés par l'article sont uniquement des corrections **topologiques** : seulement la manière dont les éléments sont connectés est changée.
Il n'y a donc aucun changement **visuel** entre la surface d'entrée et la surface de sortie.

# **Résultats** ![](./images/resultat.png)

Étant donné que les opérations réalisées par notre application sont uniquement liées à la topologie des maillages et non à la géométrie, il est assez compliqué de présenter des résultats visuels qui mettent en évidence le travail effectué par notre application.
Les captures d'écran suivantes sont tirées du logiciel MeshLab, logiciel permettant de visualiser des maillages et qui permet de mettre en avant de nombreuses caractéristiques sur ceux-ci, notamment la connectivité entre les faces.

L'image suivante présente le maillage que l'on souhaite réparer et qui présente une arête singulière (l'arête commune aux deux parallélépipèdes).

![maillage_origine](images/2_rectangles.png)

Ce maillage présentant une singularité topologique, il ne peut être chargé correctement par Radium.
En effet, les faces présentant des singularités topologiques ne sont pas ajoutées au maillage chargé par Radium, ce qui nous donne le maillage suivant :

![maillage_charge](images/2_rectangles_radium.png)

Une fois la réparation effectuée, le maillage d'origine est bien reconstruit, en supprimant les singularités topologiques (ici, dans l'exemple choisi, l'arête singulière est *dupliquée*).
Pour cela, on procède à une déconnexion des faces, une multiplication des sommets et enfin, une reconnexion des faces.
Le résultat suivant correspond au maillage obtenu après l'application de notre correction.
Les faces en rouge correspondent aux faces connectées entre elles (possédant au moins une arête commune).
Comme on peut le voir, le parallélépipède de gauche est correctement traité.
Cependant, toutes les faces du parallélépipède de droite n'ont pas été reconnectées et cela constitue donc une piste d'amélioration.
En effet, même si la correction apportée au maillage fonctionne (le maillage résultant ne présente plus de singularités), il reste cependant optimisable, en reconnectant encore certaines faces, afin que le maillage résultant soit moins lourd (possède moins de sommets).

<div style="display:flex;flex-direction:row">
<img src="images/2_rectangles_left.png" width="50%" height="auto" style="margin:5px">
<img src="images/2_rectangles_right.png" width="50%" height="auto" style="margin:5px">
</div>

# **Notre équipe** ![](./images/equipe.png)

**BARROSO** Laura

**BOUYRIE** Martin

**EGNER** Sébastien

# **Livrables** ![](./images/livrable.png)

**Méthodes et Algorithmes :** [Rapport](./livrables/Chef_doeuvre_BARROSO_BOUYRIE_EGNER.pdf) et [diapositives de notre présentantsentation](./livrables/presentation_methodes_algorithmes.pdf)

**Spécifications :** [Rapport](./livrables/Chef_d_Oeuvre_Specifications.pdf) et [diapositives de notre présentation](./livrables/Presentation Specification CO.pdf)

**Conception :** [Rapport](./livrables/CO_Conception_BARROSO_BOUYRIE_EGNER.pdf) et [diapositives de notre présentation](./livrables/Presentation Conception Co.pdf)

**Recette :** [Rapport](./livrables/Chef_doeuvre_recette_BARROSO_BOUYRIE_EGNER.pdf) et [diapositives de notre présentation](./livrables/Presentation Recette CO.pdf)
