ForceDesign by kill0rz (C) 2014 - visit kill0rz.com

Copyright
#########

Dieser Hack darf �berall zum Download angeboten werden, auch mit ver�nderten Dateien. Es muss aber immer dieser Copyrightvermerk enthalten sein!
Ver�nderungen sind zu Kennzeichnen und in der jeweiligen Installationsanleitung zu vermerken.

Beschreibung
############

Dieser Hack ist nur eine kleine Eerweiterung, um bei allen Usern ein WBB-Design gezwungen zu setzen.
Solange der Hack aktiviert ist, wird ausschlie�lich dieses eine Design verwendet. Die User k�nnen den Style zwar beliebig �ndern, und die �nderung wird in der Datenbank auch �bernommen, aber sie zeigt erst Wirkung, wenn der Hack wieder dekativiert wurde.


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
F�ge dar�ber ein:#
##################

//$forcedesignid = 0;




#######
Suche:#
#######


$result = $db->unbuffered_query("SELECT * FROM bb".$n."_designelements WHERE designpackid = '$wbbuserdata[designpackid]'");


##################
F�ge dar�ber ein:#
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
F�ge dar�ber ein:#
##################

//ForceDesign v1 by kill0rz - 10.06.2014 *Anfang*

$wbbuserdata['styleid'] = $origboardstyle;

//ForceDesign v1 by kill0rz - 10.06.2014 *Ende*


Benutzung
#########

Aktivieren:		Entferne in der zuerst eingef�gten Zeile die // und �ndere die Zahl auf das Design ab, das benutzt werden soll.
Deaktivieren:	Setze die // wieder vor die Zeile.

Beispiele aktiv: 

				$forcedesignid = 0;
				$forcedesignid = 10;
				$forcedesignid = 25;
				
Beispiele inaktiv:
				//$forcedesignid = 0;
				//$forcedesignid = 10;
				//$forcedesignid = 25;
				
				
				
Viel Spa� bei der Benutzung. Tipp: Nutze den Hack nicht zu oft, das k�nnte die User ver�rgern ;)

kill0rz