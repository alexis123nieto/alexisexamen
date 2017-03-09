    <?php
        $db_host = "am1shyeyqbxzy8gc.cbetxkdyhwsb.us-east-1.rds.amazonaws.com";
        $db_name = "zxl4lpl8325rqc9l";
        $db_user = "j2qv3f0n8u3tzlnr";
        $db_password = "l94l5lhblg7e21ds";
  
  $connection = mysql_connect($db_host, $db_user, $db_password) or die("Connection Error: " . mysql_error());
  mysql_select_db($db_name) or die("Error al seleccionar la base de datos:".mysql_error());
  @mysql_query("SET NAMES 'utf8'");

	if(isset($_POST["id_contacto"])){

$id_contacto = $_POST["id_contacto"];
$sql_query = "SELECT * FROM contactos WHERE id_contacto=$id_contacto;";
$result = mysql_query($sql_query);
$rows = array();
while($r = mysql_fetch_assoc($result)) {
$rows[] = $r;
}
print json_encode($rows);
}else
echo "No existe el contacto";
mysql_close($connection);
?>
