# grdf2influx2
Après récupération manuelle du fichier sur le site GRDF, les données sont transmises dans Influx2.0.
+ Un dashboard Grafana pour les visualiser

Tout ça largement inspiré par ce magnifique travail : [https://github.com/yukulehe/gazpar2mqtt](url)

# Information :

Les paramétres à adapter : 

#______________________
# Variables à adapter #
#______________________

# Chemin du fichier excel d'extraction GRDF le plus récent 

inputExcelFile = max(glob.glob('/home/airvb/Téléchargements/Donnees_informatives_*.xlsx'))

# Url serveur influx
url="http://192.168.88.150:8086"

# Doivent déja être créés dans influxdb  

orga = "TEST"
bucket = "ESSAI"
token = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

prix_fixe = 0.720 # prix par jour de l'abonnement
prix_kwh = 0.0942 # prix du kwh


