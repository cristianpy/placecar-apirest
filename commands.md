INSTALLATION NODEJS
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs

INSTALLATION GIT
sudo apt-get install git

INSTALLATION MYSQL
Mediante GoogleCloud

MODEL AND MIGRATION GENERATION COMMANDS

//Generation of model/migration for user
sequelize model:generate --name User --attributes name:string,email:string,password:string,phone:string,photUrl:string,role:integer

//Generation of model/migration for city
sequelize model:generate --name City --attributes name:string

//Generation of model/migration for parking
sequelize model:generate --name Parking --attributes name:string,description:text,document:string,owner:string,cityId:integer,address:string,latitude:string,longitude:string

//Generation of model/migration for reservation
sequelize model:generate --name Reservation --attributes parkingId:integer,userId:integer,type:string, quantity:decimal,price:decimal,timeStamp:date

//Generation of model/migration for parkings prices
sequelize model:generate --name ParkingPrice --attributes parkingId:integer,type:integer,quantity:decimal,price:decimal

//Generation of model/migration for parkings ratings
sequelize model:generate --name ParkingRating --attributes parkingId:integer,userId:integer,rating:decimal,timeStamp:date

//Generation of model/migration for parkings comments
sequelize model:generate --name ParkingComment --attributes parkingId:integer,userId:integer,comment:text,timeStamp:date

//Generation of model/migration for parkings images
sequelize model:generate --name ParkingImage --attributes parkingId:integer,imageUrl:string

//Generation of model/migration for payment
sequelize model:generate --name Payment --attributes reservationId:integer,paymentMethodId:integer,price:decimal,timeStamp:date

OTHER COMMANDS SEQUELIZE
sequelize db:migrate --env production 

RENAME FILE IN PROJECT
Rename file config/config.template.json to config/config.json --> npm start for verify conection

COMMANDS FOR THE CREATION OF GLOBAL VARIABLES IN NODEJS
//Location
sudo nano /etc/profile
//Commands
export username=root
export password=admin
export host=localhost
export dialect=mysql
export database=database_development
export port_db=3306
export use_env_variable=true
export secret=secret
export PORT=3000
export NODE_ENV=development
//Usage on nodejs api
process.env.PORT

//INSTALL AS A SERVICE
npm install -g forever forever-service
sudo forever-service install placecar-api --script index.js -e "NODE_ENV=production PORT=3000" --start
*/Commands to interact with service placecar-api
Start   - "sudo service placecar-api start"
Stop    - "sudo service placecar-api stop"
Status  - "sudo service placecar-api status"
Restart - "sudo service placecar-api restart"*/

CONSULTING FOR CEDULA
https://servicios.set.gov.py/eset-publico/ciudadano/recuperar?cedula=4175744

PAYMENT METHODS
https://www.pagopar.com
https://www.bancard.com.py/
https://www.2checkout.com/
