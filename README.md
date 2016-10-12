# MongoDB 
Folderstructuur, scripts, configuratie en data locatie voor Mongo DB deployment   
[Documentatie versie 2.6](https://docs.mongodb.com/v2.6/)   

## Installatie
   
###  MongoDB - NoSQL database systeem versie 2.6   
  Installatie van een centrale Mongo applicatie waar alle meteor applicaties mee kunnen verbinden.   
  [Mongo download center](https://www.mongodb.com/download-center#community)       
  Kies 'Previous Releases' en download msi versie 2.6.12 for Windows server R2 en volg de instructies:  
  ![Mongo 2.6. download](images/mongo26.png)   
  Mongo wordt in een van de standaard Windows folders geinstalleerd C:\Program Files of C:\Program Files (x86).   

## Folderstructuur  
De folderstructuur als het zip bestand wordt uitgepakt op schijf C:   
    
    C:\mongodb\
     |-- config\
     |     mongo.config           # Configuratie om MongoDB als service te starten
     |     mongoSchijfD.config    # idem als folderstructuur op schijf D is geplaatst
     |-- data\                    # centrale locatie voor alle databases van de mongo service
     |-- dump\                    # mogelijke lokatie voor backups
     |-- logs\                    # mongo log files
     |-- scripts\                 # backup en restore scripts
     |     mongo-backup.bat
     |     mongo-restore.bat

## Mongo als service
Maak een mongoDB service als volgt:   
Open een terminal en ga naar de installatie folder van Mongo bijvoorbeeld C:\Program Files\MongoDB 2.6 Standard\bin\.   
Voer uit:   
``C:\Program Files\MongoDB 2.6 Standard\bin> mongod --config  C:\mongodb\mongo.config --install``   

## Backup en Restore
Scripts voor Mongo DB backup / restore.   

### Backup
Om de gegevens te backuppen:  
1. voer het script ``mongo-backup`` uit voor de betreffende database.   
   ``mongo-backup.bat [folder voor database backup] [database naam]``  
   Voorbeeld:   
   ``mongo-backup.bat C:\backup\geoide-composer geoide-composer-test``  
   NB. In de opgegeven backup folder wordt een subfolder gemaakt met de naam van de database.

### Restore
Om de gegevens te herstellen:  
1. voer het script ``mongo-restore`` uit voor de betreffende database.  
   ``mongo-restore.bat [folder van database backup\subfolder met database backup] [database naam]``  
   Voorbeeld:   
   ``mongo-restore.bat C:\backup\geoide-composer\geoide-composer-test geoide-composer-test ``  
   NB. bij restore wordt de bestaande database overschreven met de gegevens uit de restore folder.  

