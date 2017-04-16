Autorisation firewall
=================

* Se déplacer dans le répertoire : /etc/firewalld/services
* (Chemin déprécié : /usr/lib/firewalld/services/)
* Créer le fichier plexmediaserver.xml
* Ajouter le contenu ci-dessous.

<pre>
<?xml version="1.0" encoding="utf-8"?>
<service>
  <short>Plex Media Server</short>
  <description>This opens up PlexMediaServer for http (32400), upnp, and autodiscovery.</description>
  <port protocol="tcp" port="32469"/>
  <port protocol="udp" port="32413"/>
  <port protocol="udp" port="1900"/>
  <port protocol="tcp" port="32400"/>
  <port protocol="udp" port="32412"/>
  <port protocol="udp" port="32410"/>
  <port protocol="udp" port="32414"/>
</service>
</pre>

* Lancer la commande :

<pre>
firewall-cmd --permanent --zone=public --add-service=plexmediaserver
</pre>