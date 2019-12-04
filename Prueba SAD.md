```Powershell
#Realizar un script que comprobar el puerto 80 de todas las direcciones IP

foreach($pri in 1..254){

foreach($primer in 1..254)
{
    foreach($segundo in 1..254)
    {
        foreach($tercero in 1..254)
        {
            $ip=("$pri"+"."+$primer+"."+$segundo+"."+$tercero)

            $tcpClient = New-Object System.Net.Sockets.TCPClient
            $tcpClient.Connect($ip,80)
            if($tcpClient.Connected)
            {
               echo "El puerto 80 esta abirto con esta IP:" $ip 

            }
        }
    }
}
}
####Comprobar si una IP exite 

$andel = (Resolve-DnsName andel.es)
$ip =($andel.IPADDRESS[1])


$resultadoping = ping $ipandel

if($resultadoping -match 'tiempo')
{
      "Andel tiene página web"
    (Invoke-WebRequest $ip)
    Start-Process Chrome $ip
}
else
{
    
    "Andel no tiene página web "
}
###########Comprueba si la ip tiene página web
$ErrorActionPreference = "SilentlyContinue"
foreach($pri in 1..254){

foreach($primer in 1..254){
    foreach($segundo in 1..254){
        foreach($tercero in 1..254){
            $ip=("$pri"+"."+$primer+"."+$segundo+"."+$tercero) 
            $resultadoping = ping $ip   
                 if($resultadoping -match 'tiempo'){
                 $ip
                         if (((Invoke-WebRequest $ip).StatusCode )  -eq 200){
                                $ip 
                             "Si tiene página web"
                            }
                
                }  
           }

        }
    }
}

´´´
   

 
