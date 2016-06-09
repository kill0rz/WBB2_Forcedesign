ForceDesign by kill0rz (C) 2014 - visit kill0rz.com

Copyright
#########

Dieser Hack darf überall zum Download angeboten werden, auch mit veränderten Dateien. Es muss aber immer dieser Copyrightvermerk enthalten sein!
Veränderungen sind zu Kennzeichnen und in der jeweiligen Installationsanleitung zu vermerken.

Beschreibung
############

Dieser Hack ist nur eine kleine Eerweiterung, um bei allen Usern ein WBB-Design gezwungen zu setzen.
Solange der Hack aktiviert ist, wird ausschließlich dieses eine Design verwendet. Die User können den Style zwar beliebig ändern, und die Änderung wird in der Datenbank auch übernommen, aber sie zeigt erst Wirkung, wenn der Hack wieder dekativiert wurde.


Changelog
#########

v1.0 (10.06.2014)
----
Grundskript


Installtion
###########

Datei: global.php
====== --------

#######
Suche:#
#######


/** get function libary **/


##################
Füge darüber ein:#
##################

//$forcedesignid = 0;




#######
Suche:#
#######


$result = $db->unbuffered_query("SELECT * FROM bb".$n."_designelements WHERE designpackid = '$wbbuserdata[designpackid]'");


##################
Füge darüber ein:#
##################

//ForceDesign v1 by kill0rz - 10.06.2014 *Anfang*

$origboardstyle = $wbbuserdata['styleid'];
if (isset($forcedesignid)) {
	$style = $db->query_first("SELECT s.styleid, s.templatepackid, s.designpackid, tp.templatestructure FROM bb" . $n . "_styles s LEFT JOIN bb" . $n . "_templatepacks tp ON(tp.templatepackid=s.templatepackid) WHERE s.styleid = '$forcedesignid'");
	$wbbuserdata['designpackid'] = $style['designpackid'];
	$wbbuserdata['templatepackid'] = $style['templatepackid'];
	$wbbuserdata['styleid'] = $style['styleid'];
	$wbbuserdata['templatestructure'] = $style['templatestructure'];
}

//ForceDesign v1 by kill0rz - 10.06.2014 *Ende*




#######
Suche:#
#######


?>


##################
Füge darüber ein:#
##################

//ForceDesign v1 by kill0rz - 10.06.2014 *Anfang*

$wbbuserdata['styleid'] = $origboardstyle;

//ForceDesign v1 by kill0rz - 10.06.2014 *Ende*


Benutzung
#########

Aktivieren:		Entferne in der zuerst eingefügten Zeile die // und ändere die Zahl auf das Design ab, das benutzt werden soll.
Deaktivieren:	Setze die // wieder vor die Zeile.

Beispiele aktiv: 

				$forcedesignid = 0;
				$forcedesignid = 10;
				$forcedesignid = 25;
				
Beispiele inaktiv:
				//$forcedesignid = 0;
				//$forcedesignid = 10;
				//$forcedesignid = 25;
				
				
				
Viel Spaß bei der Benutzung. Tipp: Nutze den Hack nicht zu oft, das könnte die User verärgern ;)

kill0rz