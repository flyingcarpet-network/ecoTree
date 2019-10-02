# EcoTree Database Structure & Proposed Smart Contract Data Storage

This file serves to outline EcoTree's current database structure and the proposed associated data to be stored on-chain.

The following represents the fields associated with each "division" (or smallest unit of account of EcoTree's forest land):

```division :
  id :  '31'
  essence:  '2'  # tree type internal id
  essence_name: 'Douglas'
  parcelle: '3'   # plot of land internal id
  parcelle_name: , 'Langoëlan ZW 5', # plot of land internal name
  date_plantation : '1977-01-01' # date planted
  date_coupe: , NULL, # date cut
  polygone : '[[48.14397928306157,-3.269692503800084], ..' # GPS polygon on the plot of land
  cubage: 40 # expected production in cubic meters at date of cutting
  ageMaturiteCoupe: 60 # age when we expect to cut the trees 
  futaie_irreguliere: 1 # are all the trees in parcelle of same species/age etc. or is it mixed up ?
  type_gestion: 'Futaie mixte avec objectif de régénération naturelle.' #forest maagement type 
  geologie_type_sol: 'leucogranites de Pontivy (granites à grain moyen, à deux micas) .' # geology / ground type 
  foret_id: '2', 
  foret_name: 'Forêt de Brokus'
  ```

While all of these fields are stored for each individual division in EcoTree's SQL database, the Asset Ownership Contract does not require redundancy of these data fields. Instead, the smart contract simply stores a hash, for each division, of all of the fields of the data fields contained within that division—omitting any fields (from the data to be hashed) that have the capacity to change.

Thus, after a division has been approved by the AMF, added to the SQL database, and recorded on-chain, in order for it to be evaulated as "valid", its data may be hashed and checked against the Asset Ownership Contract's saved hash of the division's data.
