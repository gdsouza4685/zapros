<?php
$servername = "192.168.1.72:5677"; 
$username = "root"; 
$password = "AITYwRISHOtA"; 
$dbname = "ABC"; 

// Create connection 
$conn = mysqli_connect($servername, $username, $password, $dbname);
// Check connection 
if ($conn->connect_error) { 
    die("Connection failed: " . $conn->connect_error); 
}

date_default_timezone_set('Russia/Moskow');
$date = date("d.m.Y h:i");

$create = "CREATE TABLE `ABC`.`$date` ( `Код` VARCHAR(256) NOT NULL , `Код поставщика` VARCHAR(256) NOT NULL , `Наименование` VARCHAR(256) NOT NULL , `CastoramaABC` INT NOT NULL , `LiderVrn` INT NOT NULL ,`Chipak71` INT NOT NULL , `TdKvartalABC` INT NOT NULL , `VoronezhPoryadok` INT NOT NULL , `Et48` INT NOT NULL , `Minimaks` INT NOT NULL , `Vashdom24` INT NOT NULL , `Yugkabel` INT NOT NULL , `Amperkin` INT NOT NULL , `Etm` INT NOT NULL , `KRDElectro` INT NOT NULL , `Rs24` INT NOT NULL , `EtkElectric` INT NOT NULL , `Elm48ABC` INT NOT NULL ,`Lt46` INT NOT NULL , `RndElectroABC` INT NOT NULL , `Silatoka68ABC` INT NOT NULL , `Svetitled` INT NOT NULL , `TandemToolsABC` INT NOT NULL , `Tse46` INT NOT NULL , `ElekR` INT NOT NULL ) ENGINE = InnoDB;";
        
            $sql = ($create); 
            if ($conn->query($sql) === TRUE) { 
                echo "Работает - "; 
            } else { 
                echo "Не Работает" . $conn->error; 
            }


$i = 0;
while ($i <= 1000) {

$i++;

$ch = curl_init("https://allrival.com/api/v1/secured/report/similars?filter[_page]=$i&filter[_per_page]=500");
curl_setopt($ch, CURLOPT_HTTPHEADER, array('X-AUTH-TOKEN:1b9f3e24-64a4-48d4-a4da-5af1a022dc29'));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_HEADER, false);
$html = curl_exec($ch);
curl_close($ch);

$arr = json_decode($html, true); // получим ассоциативный массив


echo "<pre>";
foreach($arr['items'] as $itemitem => $item)
{ 

    $kod = ($item['external_id']);
    $kod_post = ($item['attributes']['MANUF_VENDOR_CODE']);
    $name = ($item['name']);

    
    $create = "INSERT INTO `$date`(`Код`,`Код поставщика`,`Наименование`) VALUES ('$kod','$kod_post','$name');";
 
        $sql = ($create); 
        if ($conn->query($sql) === TRUE) { 
            echo "Работает - "; 
        } else { 
            echo "Не Работает" . $conn->error; 
        }


        foreach($item['rivals'] as $rivalname => $rivals){
        
          
            

            $CastoramaABC = ($item['rivals']['CastoramaABC']['price']);
            $LiderVrn = ($item['rivals']['LiderVrn']['price']);
            $Chipak71 = ($item['rivals']['Chipak71']['price']);
            $TdKvartalABC = ($item['rivals']['TdKvartalABC']['price']);
            $VoronezhPoryadok = ($item['rivals']['VoronezhPoryadok']['price']);
            $Et48 = ($item['rivals']['Et48']['price']);
            $Minimaks = ($item['rivals']['Minimaks']['price']);
            $Vashdom24 = ($item['rivals']['Vashdom24']['price']);
            $Yugkabel = ($item['rivals']['Yugkabel']['price']);
            $Amperkin = ($item['rivals']['Amperkin']['price']);
            $Etm = ($item['rivals']['Etm']['price']);
            $KRDElectro = ($item['rivals']['KRDElectro']['price']);
            $Rs24 = ($item['rivals']['Rs24']['price']);
            $EtkElectric = ($item['rivals']['EtkElectric']['price']);
            $Elm48ABC = ($item['rivals']['Elm48ABC']['price']);
            $Lt46 = ($item['rivals']['Lt46']['price']);
            $RndElectroABC = ($item['rivals']['RndElectroABC']['price']);
            $Silatoka68ABC = ($item['rivals']['Silatoka68ABC']['price']);
            $Svetitled = ($item['rivals']['Svetitled']['price']);
            $TandemToolsABC = ($item['rivals']['TandemToolsABC']['price']);
            $Tse46 = ($item['rivals']['Tse46']['price']);
            $ElekR = ($item['rivals']['ElekR']['price']);
            

            
            $create = "UPDATE `$date` SET `CastoramaABC`='$CastoramaABC',`LiderVrn`='$LiderVrn',`Chipak71`='$Chipak71',`TdKvartalABC`='$TdKvartalABC',`VoronezhPoryadok`='$VoronezhPoryadok',`Et48`='$Et48',`Minimaks`='$Minimaks',`Vashdom24`='$Vashdom24',`Yugkabel`='$Yugkabel',`Amperkin`='$Amperkin',`Etm`='$Etm',`KRDElectro`='$KRDElectro',`Rs24`='$Rs24',`EtkElectric`='$EtkElectric',`Elm48ABC`='$Elm48ABC',`Lt46`='$Lt46',`RndElectroABC`='$RndElectroABC',`Silatoka68ABC`='$Silatoka68ABC',`Svetitled`='$Svetitled',`TandemToolsABC`='$TandemToolsABC',`Tse46`='$Tse46',`ElekR`='$ElekR' WHERE `Наименование`='$name';";
        
            $sql = ($create); 
            if ($conn->query($sql) === TRUE) { 
                echo "Работает - "; 
            } else { 
                echo "Не Работает" . $conn->error; 
            }
    
        };
    

};
echo "</pre>";




}
$conn->close();
?>

