# unbound

Serveur DNS recursif

* utilise les variables `our_domains` et `private_domains` pour les zones 'locales'
  (stub-zones)
* autorise `our_nets` et `private_nets`
* ecoute sur `unbound_interfaces` (ou toutes les adresses par défaut)
* redirige les requetes vers `unbound_forwarders` s'ils existent

## variables

* `unbound_interfaces ([])`
  IP's to listen to
* `unbound_port (53)`
* `our_nets ([])`
  allowed public networks
* `private_nets ([])`
  allowed AND protected private networks
* `our_domains ([])`
  direct access to our public domains
  eg: - { name: "univ.fr.", masters: [ "192.168.1.1", "192.168.1.2@5353" ] }
* `private_domains ([])`
  domains allowed to contain `private_nets` IP's (and config stub-zone)
  same syntax as `our_domains`
* `unbound_nodefault ([])`
  RFC1918/RFC3330/RFC4291/RFC4193/RFC4291/RFC7686 local zones
  eg: - 168.192.in-addr.arpa.
* `unbound_forwarders ([])`
  eventual forwarders
* `unbound_forward_domains ([])`
  forward-zones
  same syntax as `our_domains`, but 'master' MUST be a resolver itself
* `unbound_dns64_prefix ("")`
* `unbound_dns64 (False)`
  Enable DNS64

