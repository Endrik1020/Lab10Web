# Lab10Web
# Praktikum 10

~~~
Nama  : Endrik
NIM   : 311910088
Kelas : TI.19.C1
~~~

# Langkah-langkah Praktikum
Buat folder baru dengan nama lab10_php_oop pada docroot webserver (htdocs)
![1](https://user-images.githubusercontent.com/81820421/122060254-9e47b000-ce17-11eb-964f-3ce699fa5cfa.JPG)
# Buat file baru dengan nama mobil.php
~~~
<?php 
/**
 * Program sederhana pendefinisian class dan pemanggilan class
 **/

 class Mobil
 {
     private $warna;
     private $merk;
     private $harga;

     public function __construct()
     {
         $this->warna = "Biru";
         $this->merk = "BMW";
         $this->harga = "10000000";
     }

     public function gantiWarna ($warnaBaru)
     {
         $this->warna = $warnaBaru;
     }

     public function tampilWarna()
     {
         echo "Warna mobilnya : " . $this->warna;
     }
 }

//  membuat objek mmobil
$a = new Mobil();
$b = new Mobil();

// memangging objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();

?>
~~~
![2](https://user-images.githubusercontent.com/81820421/122060763-11e9bd00-ce18-11eb-8893-5b028baf4fb3.JPG)

# Buat file baru dengan nama form.php
~~~
<?php 
/**
 * Nama Class : Form
 * Deskripsi : Class untuk membuat forminputan text sederhana
 */

 class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Formm";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }

    public function displayForm()
    {
        echo "<form action='".$this->action."' method='POST'>";
        echo '<table width="100%" border="0">';
        for ($j=0; $j<count($this->fields); $j++) {
            echo 
            "<tr>
                <td
                    align='right'>".$this->fields[$j]['label'].
                "</td>";
            echo 
                "<td>
                    <input type='text' name='".$this->fields[$j]['name']."'>
                </td>
            </tr>";
        }

    
        echo
        "<tr>
            <td colspan='2'>";
                "<input type='submit' value='".$this->submit."'>
            </td>
        </tr>";
        echo "</table>";
    }

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}
?>
~~~
![3](https://user-images.githubusercontent.com/81820421/122061137-6ee57300-ce18-11eb-94a8-449800d1fe0d.JPG)

# Buat file baru dengan nama form_input.php
~~~
<?php 
/**
 * Program pemanfaatan Program 10.2 untuk membuat form inputan sederhana.
 */

 include "form.php";

 echo "<html><head><title>Mahasiswa</title></head><body>";
 $form = new Form("","Input Form");
 $form->addField("txtnim", "Nim");
 $form->addField("txtnama", "Nama");
 $form->addField("txtalamat", "Alamat");
 echo "<h3>Silahkan isi form berikut ini : </h3>";
 $form->displayForm();
 echo "</body></html>"

?>
~~~
![4](https://user-images.githubusercontent.com/81820421/122061489-c1bf2a80-ce18-11eb-8b1b-37e31e294d3a.JPG)



