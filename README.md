practica amo mucho
[practica1.html](https://github.com/user-attachments/files/22248196/practica1.html)

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    aplicacion web

</head>
<body>
    <CENTER><h1>BIENVENIDO A MI SITIO WEB</h1>
    <P>Este sitio esta en construccion para mejorar para el mundo </P></CENTER>
    
</body>
</html>


[producto.html](https://github.com/user-attachments/files/22248260/producto.html)

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .imagen-circular{
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 100%;
        }
        body{
            background-image:url(futbool1.jpeg) ;
            background-repeat: no-repeat;
            background-size: cover;width: 100%;height: 400px;
           

        }
        #t{
            
            font-size: 50px;
            height: 60px;
            width: 700px;
        }
        #t1{
            margin-left: 100px;
            font-size: 60px;
            border-radius: 5.0em;
            background-color: transparent;
        }
        #t1:hover{
            background-color: black;
            font-size: 60px;
            border-radius: 5.0em;
            color: blue;
            
        }
        #t3{
            text-align: 300px;
        }
        #t4{
            width: 500px;
            font-size: 500px;
        }
        #t5{
            font-size: 50px;
        }
        #b{
        color: rgb(9, 13, 16);
        font-size: 60px;
        border-style: solid;
        border-radius: 0.5em;
        height: 50%;
        width: 50%;
     }
     #b:hover{
        color: aliceblue;
        font-size: 60px;
        border-style: solid;
        border-radius: 0.5em;
        height: 50%;
        width: 50%;
        background-color: brown;
     }
     
     
    </style>
    <script>
        function inicio(){
            window.open("inicio.html")
        }
        function producto(){
            window.open("producto.html")
        }
        function contacto(){
            window.open("contacto.html")
        }
    
        function basquet(){
            window.open("basquet.html")
        }
    
</script>
</head>
<body >
<header> <img src="logo.jpeg" alt=" imagen" class="imagen-circular" >
<center><input type="submit" value="INICIO" id="t1" onclick="inicio()"> 
<input type="submit" value="PRODUCTO" id="t1" onclick="producto()">
<input type="submit" value="CONTACTO" id="t1" onclick=" contacto()"></center>
</header> <br>
<center><p1 id="t">Futbool</p1><br><br>
<p id="t">Lo mejor de lo mejor </p></center>

<center><p2 id="t5"> Marcas  de Balones</p2><br><br></center>
<input type="checkbox" name="c" id="" >Futtree <img src="D_NQ_NP_717362-MLM40545439220_012020-O.webp" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Nike <img src="Unknown-8.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Voit <img src="Unknown-7.jpeg" alt="" width="200px" height="200px"><br>
<input type="checkbox" name="c" id=""> Gaser <img src="Unknown-9.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Molten <img src="Unknown-10.jpeg" alt="" width="200px" height="200px"><br>
<select name="" id="t4"> 
    <option value="">seleccione color del balon  </option>
    <option value="">Rojo y Negro</option>
    <option value="">Verde y Amarillo </option>
    <option value="">Azul y Naranja </option>
    <option value="">Gris y Negro</option>
    <option value="">naranja y Verde</option>
</select> <br><br>

<center><p3 id="t5">Uniforme de Futbool</p3><br></center>

<input type="checkbox" name="c" id="" >Real madrid <img src="Unknown-2 copy.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Barcelona <img src="Unknown-3.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Manchester city <img src="nuevo-uniforme-manchester-city-2018.jpg.webp" alt="" width="200px" height="200px"><br>
<input type="checkbox" name="c" id=""> Manchestar unaiter <img src="Unknown-4.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Liverpool <img src="liverpool.jpeg" alt="" width="200px" height="200px">
<input type="checkbox" name="c" id=""> Arsenal <img src="Unknown-6.jpeg" alt="" width="200px" height="200px"><br>
<input type="checkbox" name="c" id=""> Juventus  <img src="Unknown-5.jpeg" alt="" width="200px" height="200px"><br><br>
  
<center><p4 id="t5"> Como seria el uniforme de las mangas</p4><br></center>
<center><input type="radio" name="c" id="">Manga larga <input type="radio" name="c" id="">Manga corta <br></center>
<select name="" id="t4"> 
    <option value="">color de el uniforme </option>
    <option value="">Negro</option>
    <option value="">Blanco</option>
    <option value="">Azul  </option>
    <option value="">rojo</option>
    <option value="">Gris</option>
</select> <br><br>

<center><p5 id="t5">Tacos deportivos que quiere </p3><br></center>
<input type="radio" name="c" id="" >Adidas <img src="images-1.jpeg" alt="" width="200px" height="200px">
<input type="radio" name="c" id=""> Nike   <img src="images-2.jpeg" alt="" width="200px" height="200px">
<input type="radio" name="c" id=""> Pirma  <img src="Unknown-11.jpeg" alt="" width="200px" height="200px"><br>   


    <center><P6 id="t5"> Que color serian</P6><br></center>
<select name="" id="t4"> 
    <option value="">sellecione color </option>
    <option value="">Negros</option>
    <option value="">Blancos </option>
    <option value="">Azul  </option>
    <option value="">rojos</option>
    <option value="">Grises</option>
</select> <br><br> <br><br>

<center><label id="b" onclick="basquet()">basquet</label></center>


</body>
</html>
