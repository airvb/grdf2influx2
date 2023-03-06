# grdf2influx2
Après récupération manuelle du fichier sur le site GRDF, les données sont transmises dans Influx2.0.
+ Un dashboard Grafana pour les visualiser

Tout ça largement inspiré par ce magnifique travail : [https://github.com/yukulehe/gazpar2mqtt](url)

# Information :

Les paramétres à adapter dans le fichier **grdf2influx.py**

### Chemin du fichier excel d'extraction GRDF 

inputExcelFile = max(glob.glob('**/home/airvb/Téléchargements**/Donnees_informatives_*.xlsx'))

### url serveur influx

url="**http://192.168.88.150:8086**"

### Doivent déja être créés dans influxdb 
orga = "**TEST**"

bucket = "**ESSAI**"

token = "**xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx**"

prix_fixe = **0.720** # prix par jour de l'abonnement

prix_kwh = **0.0942** # prix du kwh

# Utilisation
Récuperer sur le site https://monespace.grdf.fr la consommation détaillée **par jour**

![This is an image](https://i.imgur.com/d8V8U8b.png)

Puis 

![This is an image](https://i.imgur.com/ThJr0Sk.png)

Le fichier est téléchargé ( dans le dossier ~/Téléchargement)                  <--- **A Adapter ds les paramétres**.

![This is an image](https://i.imgur.com/7LP4eSe.png)

Il suffit ensuite de lancer le script python : **grdf2influx2.py**

Il va utiliser le dernier fichier téléchargé et inserer dans le bucket les nouvelles données.

```:~/data_gaz$ ./grdf2influx2.py 
Début
Verification connection Influx... Connexion Influx >  Ok influx
Calcul coût
Premiere date du fichier: 07/03/2020
Derniere date enregistrée ds influx: 03/03/2023
Derniere date du fichier d'import :  03/03/2023
Terminé , 0 jours ajoutés.
```

Résultat dans grafana :
![This is an image](https://i.imgur.com/0Ney8HR.png)


# Test
Comme je dis toujours, je ne suis pas développeur. 
L’objectif de mes programmes, c’est de faire fonctionner le projet. 
Il ya probablement des quantités d'amélioration possible.


![This is an image](https://github.com/airvb/grdf2influx2/blob/35c6079d74667543ede6f436df31017d0d43e131/grdf2influx.png)
