# mongodb
Scripts voor Mongo DB deployment.   
Voer de backup uit op de machine waarop de Composer (en de Geoide viewer) geïnstalleerd staat.
Mongodb draait standaard op poort 27017 (localhost:27017)  

Omdat de Mongo installatie de mongo programma's niet in het Windows PATH zet, moeten de scripts als volgt worden gestart:    
Open een terminal (DOS prompt) en ga naar C:\Program Files\MongoDB 2.6 Standard\bin\   


## Backup
Om de gegevens te backuppen:  
1. voer het script ``mongo-backup`` uit voor de betreffende database   
   ``mongo-backup.bat [folder voor database backup] [database naam]``  
   Voorbeeld:   
   ``C:\mongodb\scripts\mongo-backup.bat C:\backup\geoide-composer geoide-composer-live``  
    NB. In de opgegeven backup folder wordt een subfolder gemaakt met de naam van de database 
        (dus 'geoide-composer-live' volgens het bovenstaande voorbeeld).
    NB2. Het pad naar het backup script is afhankelijk van waar de installatie staat (C,D,..)


## Restore
Om de gegevens van Geoide-Composer te herstellen:  
1. voer het script ``mongo-restore`` uit voor de betreffende database  
   ``mongo-restore.bat [folder van database backup] [database naam]``  
   Voorbeeld:   
   ``mongo-restore.bat C:\backup\geoide-composer\geoide-composer-test geoide-composer-test ``  
   NB. bij restore wordt de bestaande database overschreven met de gegevens uit de restore folder.  
    

