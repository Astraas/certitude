CERTitude
==============
Remote Python IOC scanner for Windows targets


### Ajouter un module

1. Cr�er le script d'extraction et le placer dans `ressources/`. Celui-ci doit respecter les conditions suivantes :
	- �tre �crit en Batch ou Bash.
	- Restituer les donn�es extraites dans un fichier TSV (Tab Separated Value).
2. Cr�er le fichier .sql associ� r�alisant l'importation
3. Cr�er le contr�leur associ� dans les r�pertoires `flatevaluators/` et/ou `logicevaluators`.
4. Lier le contr�leur � CERTitude dans le fichier `targethandler.py` (evaluator list, drop list...)

### Modules existants

- RegistryItem
	- KeyPath
	- ValueName	
- FileItem
	- FilePath
	- FullPath
	- FileName
	- FileExtension	
- Services
	- name
	- descriptiveName
	- path
	- pathMD5Sum
	- status (i.e running / stopped)
	- mode (ie auto / on demand / delayed �)	
- ArpEntryItem
	- IPv4
	- PhysicalAddress
	- Interface
	- CacheType (static|dynamic)
	
### TODO

#### Probabilit� ++

- DnsEntryItem
	- Host
	- record_name / record_type
	- TTL
	- Data_Length
	- section
	- A_record
	- Cname
- PortItem (connexion r�seaux)
	- Local IP : Port
	- Remote IP : Port
	- State
	- Process
	- Protocol	
- PrefetchItem (si on y arrive) :
	- ApplicationFilename / FullPath
	- Hash
	- TimesExecuted	
- ProcessItem
	- Name
	- Path + MD5SUM + Strings
	- PPID
	- DLL Import�es + peut-�tre un peu d�infos sur le PE si on trouve
	- User	
- RouteEntryItem
	- Pour l�IPv4 : Destination r�seau    Masque r�seau  Adr. passerelle   Adr. interface M�trique


#### Probabilit� -

- EventLog ==> pas s�r du tout, il faut passer par WMIC, et que �a plante avec CERTitude
- Peut �tre des infos sur les UserItem

(c) Jean MARSAULT @ Solucom 2014
