# Wordpress Plugin #

### A simple PhP plugin to store data into a MySQL database at Wordpress. ###
- - - -

```
<?php
error_reporting(-1);
//  error_reporting( E_CORE_ERROR | E_CORE_WARNING | E_COMPILE_ERROR | E_ERROR | E_WARNING | E_PARSE | E_USER_ERROR | E_USER_WARNING | E_RECOVERABLE_ERROR );

	define( 'ABSPATH', dirname(__FILE__) . '/' );

  require('ABSPATH . wp-load.php' );
//    require_once('C:\wamp\www\wp-load.php');
	global $wpdb;                          //wordpress variable to handle all permissions and connections
        if (!empty($_POST)) {

            $table = info;
            $data = array(
                'name' => $_POST['name'],         //these completely depend on the structure of MySql table
                'address' => $_POST['address'],
				        'place' => $_POST['place']
            );
			//print_r($data);
            $format = array(
                '%s',
                '%s'
            );
            $success=$wpdb->insert( $table, $data, $format );
            if($success){
            echo 'Data has been saved' ;
}
else
	echo 'error occured';
}

$query = "Select * from `info`";

$return = $wpdb->get_results($query);
if($return)
	print_r($return);
else
	echo "Some error occured";

?>
```
