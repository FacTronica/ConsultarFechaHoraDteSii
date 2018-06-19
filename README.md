# ConsultarFechaHoraDteSii
<br>Webservice para obtener la fecha y hora en que un dte fue recibido y aceptado por el SII Chile.
<br>
<br>A continuación se detalla el Procedimiento a realizar:
<br>
<br>1.-Generar Archivo Plano TXT
<br>2.-Enviar Archivo Plano TXT al WebService
<br>3.-Recuperar Archivo XML con Respuesta del SII
<hr>
<h3>Proceso 1: Generar Archivo Plano</h3>
Este proceso Consiste en generar un archivo de texto plano con el formato requerido para poder realizar la consulta.
<pre>
<?php

############################ DATOS DEL DOCUMENTO #################
# RUT DEL EMISOR DEL DTE
$FACTRONICA["rutEmisor"]="10377898";
# DV RUT DEL EMISOR DEL DTE
$FACTRONICA["dvEmisor"]="0";
# TIPO DE DTE
$FACTRONICA["tipoDoc"]="33";
# FOLIO DEL DTE
$FACTRONICA["folio"]="3093";



###################################  DATOS DE COMUNICACION ##################
# AMBIENTE 0=PRUEBAS 1=PRODUCCION
$FACTRONICA["PRODUCCION"]="1";
# DIRECTORIO TEMPORAL
$FACTRONICA["DIRTEMP"]="temp"; 
# ARCHIVO PLANO QUE SERA ENVIADO AL SERVIDOR
$FACTRONICA["ARCHIVOTXT"]="temp/sutxt.txt";
# URL DONDE SERA ENVIADO EL TXT
$FACTRONICA["URLHOST"]="http://190.107.177.113/~apifactronica/factronica_aceptareclama_servidor";
# SCRIPT QUE RECIBE EL ARCHIVO TXT
$FACTRONICA["URLFILE"]="recibe_txt_aceptareclama.php";


################# NO REQUERIDAS ########################
#
$FACTRONICA["SEMILLA"]="semilla_simple.xml";
#
$FACTRONICA["SEMILLAPORFIRMAR"]="semilla_porfirmar.xml";
#
$FACTRONICA["SEMILLAFIRMADA"]="semilla_firmada.xml";
#
$FACTRONICA["DIGESTADOR"]="digestion.txt";
#
$FACTRONICA["XSDTOKEN"]="token_sii.xsd";
#
$FACTRONICA["TOKEN"]="null";
# RESPUESTA DEL SII CON FECHA Y HORA RECEPCION DEL DTE EJ.05-08-2017 11:03:51
$FACTRONICA["RESPUESTA"]="fecha_recibo.txt";


################################  CERTIFICADO #################################
# MODULO DEL CERTIFICADO
$FACTRONICA["Modulus"]="j0TDptU1Y4dysxfGe1N/3lxfb1uXnVATEEhxGOaPfCq8hciUv0eN2d2yLry0xBqV
IZaTVgfO/GJIsXIQ4eEqBduCEOjwHbLLZ28WgZMiSQXjWH9YJDyCrad2yrjPbefG
IwaorEZzpR76SjGgwIwuSt+Xa7RfpPR1E37GmOdWyIk="; 
# EXPONENTE DEL CERTIFICADO
$FACTRONICA["Exponent"]="AQAB"; 
# CERTIFICADO X509
$FACTRONICA["X509Certificate"]="MIIGMjCCBRqgAwIBAgIKSRBvTwAAAAMb0jANBgkqhkiG9w0BAQUFADCB0jELMAkG
A1UEBhMCQ0wxHTAbBgNVBAgTFFJlZ2lvbiBNZXRyb3BvbGl0YW5hMREwDwYDVQQH
Le0bsUDnrWTBWfI9hmAsfCjcKcexuBU66Hh4bZo08eOX8RgvquWBCxigeiR1VqyP
Bejh30RdAYvEop021P7nRydCh3EsXO5ImG3PtTdbH9e0Ywk6HB+LPzSF6G6KxQC8
5RhJ5Prk";
# LLAVE PRIVADA SIN CLAVE
$FACTRONICA["PrivKey"]="-----BEGIN RSA PRIVATE KEY-----
MIICXgIBAAKBgQCPRMOm1TVjh3KzF8Z7U3/eXF9vW5edUBMQSHEY5o98KryFyJS/
bZFLjsU1GXjIAMSh4dLyQd7+B1GrCL2ER4F5h1I5pdJigmGOtYM5zTHufMVwek/1
4zUvMQcW0/DCfX6hOxyFAkEAmuPTM4Ry2fsL0jGK/y0+FNOUZrMc40h6sfvfLbAN
GsNWx+48EpsjyUbytOat0JjxHABDnHvYZn9SXJimrXtJIw==
-----END RSA PRIVATE KEY-----"; 
?>
</pre>


