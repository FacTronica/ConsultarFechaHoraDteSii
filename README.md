# ConsultarFechaHoraDteSii
<br>Webservice para obtener la fecha y hora en que un dte fue recibido y aceptado por el SII Chile.
<br>En este caso y como ejemplo se utilizará con Factura tipo 33 Folio 123123 Rut Emisor 11111111-1.
<br>
<br>A continuación se detalla el Procedimiento a realizar:
<br>
<br>1.-Generar Archivo Plano TXT
<br>2.-Enviar Archivo Plano TXT al WebService
<br>3.-Recuperar Archivo XML con Respuesta del SII
<hr>
<h3>Proceso 1: Generar Archivo Plano</h3>
<br>Este proceso Consiste en generar un archivo de texto plano con el formato requerido para poder realizar la consulta.
<br>En el siguiente link encontrará el formato del archivo de texto que debe generar con su sistema.
<br>https://github.com/FacTronica/ConsultarFechaHoraDteSii/blob/master/archivo_plano.txt
<br>
<hr>
<h3>Proceso 2: Enviar Archivo Plano</h3>
<br>El archivo txt se debe enviar al webservice utilizando curl.
<br>
<br><b>Linux:</b>
<br>curl --form "archivotxt=@archivo_plano.txt"  http://190.107.177.113/~apifactronica/factronica_aceptareclama_servidor/recibe_txt_aceptareclama.php
<br>
<br><b>En Windows:</b>
<br>c:\curl\curl.exe --form "archivotxt=@c:\curl\archivo_plano.txt" http://190.107.177.113/~apifactronica/factronica_aceptareclama_servidor/recibe_txt_aceptareclama.php
<br>
<hr>
<h3>Proceso 3: Recuperar Archivo Xml con Respuesta:</h3>
<br>En este proceso se recupera el archivo xml con el resultado entregado por el sii.
<br>
<br>
<br><b>Linux:</b>
<br>curl -o estadodte_rut111111111_tipo33_folio123123.xml http://190.107.177.113/~apifactronica/factronica_aceptareclama_servidor/recibe_txt_aceptareclama.php/temp/estadodte_rut111111111_tipo33_folio123123.xml
<br>
<br>
<br><b>En Windows:</b>
<br>c:\curl\curl.exe -o c:\curl\estadodte_rut111111111_tipo33_folio123123.xml http://190.107.177.113/~apifactronica/factronica_aceptareclama_servidor/recibe_txt_aceptareclama.php/temp/estadodte_rut111111111_tipo33_folio123123.xml
<br>
<br>NOTA:
<br>En este ejemplo el archivo de salida se define en la variable $FACTRONICA["RESPUESTA"]="estadodte_rut111111111_tipo33_folio123123.xml";
