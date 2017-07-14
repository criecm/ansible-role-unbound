# unbound

Serveur DNS recursif

* utilise les variables `our_domains` et `private_domains` pour les zones 'locales'
  (stub-zones)
* autorise `our_nets` et `private_nets`
* ecoute sur `unbound_interfaces` (ou toutes les adresses par défaut)
* redirige les requetes vers `unbound_forwarders` s'ils existent


