#include <LiquidCrystal_I2C.h>
#include <RTClib.h>
#include  <Wire.h>
//#include <lcd_greek_chars.h>
#include <dht_nonblocking.h>
#include <dht11.h>
#define DHT11PIN 8

dht11 DHT11; //Αρχικοποίηση αισθητήρα θερμοκρασίας και υγρασίας

RTC_DS3231 rtc; //Αρχικοποίηση ρολογιού

LiquidCrystal_I2C lcd(0x27,  16, 4); //Αρχικοποίηση οθόνης

int relay = 11 ; //Ρελέ στη υποδοχή 3

void setup() {
  pinMode(relay, OUTPUT); //Ρελέ σε κατάσταση εξόδου
  digitalWrite(relay, LOW); //Σίγαση του ρελέ
  
  
  lcd.init(); //αρχικοποίηση lcd οθόνης
  lcd.backlight(); //ενεργοποίησε τον φωτισμό οθόνης
  
  //Σε περίπτωση που δεν μπορεί να βρεθεί το ρολόι εμφάνισε μήνημα
  if (! rtc.begin()) {
    lcd.setCursor(0,0);
    lcd.println("Couldn't find RTC");
    lcd.flush();
    while (1) delay(10);
  }
 //if (rtc.lostPower()) {
  //rtc.adjust(DateTime(F(__DATE__), F(__TIME__))); // αρχικοποίηση την ώρα σύμφωνα με την ώρα του υπολογιστή
  //January 21, 2014 at 3am you would call:
   //rtc.adjust(DateTime(2014, 1, 21, 3, 0, 0));

   
 //}
}

void loop() {
  DateTime now = rtc.now(); //Βάλε στο now την τρέχουσα ώρα

  delay(1000);//Καθυστέρησε ένα δευτερόλεπτο, για να ανανεώνει την ώρα ανά δευτερόλεπτο
  
  lcd.setCursor(0,0); //Τοποθέτησε τον κέρσορα στην πρώτη γραμμή και πρώτη στήλη στην οθόνη LCD
 
  char buf[21];
  sprintf(buf, "%02d/%02d/%04d", now.day(), now.month(), now.year());// Βάλε στο buf την ημερομηνία μορφοποιώντας την
  lcd.print(buf); // Εκτύπωσε την ημερομηνία στην οθόνη
  
  lcd.setCursor(0,1); //Τοποθέτησε τον κέρσορα στην δεύτερη γραμμή και πρώτη στήλη στην οθόνη LCD

  char buff[21];
  sprintf(buff, "%02d:%02d:%02d", now.hour(), now.minute(), now.second());// Βάλε στο buff την ημερομηνία μορφοποιώντας την
  lcd.print(buff);  // Εκτύπωσε την ημερομηνία στην οθόνη


  int chk = DHT11.read(DHT11PIN); //Βάλε στην chk τις μετρήσεις από τον αισθητήρα

  char bufff[21];
  sprintf(bufff, "%02d%% %02dC", DHT11.humidity, DHT11.temperature);// Βάλε στο bufff την ημερομηνία μορφοποιώντας την

  //lcd.print(DHT11.humidity, 10); 
  //lcd.print("%");
  lcd.setCursor(10,1); //Τοποθέτησε τον κέρσορα στην δεύτερη γραμμή και δέκατη στήλη στην οθόνη LCD

  //lcd.print(DHT11.temperature, 10);
  //  lcd.print("C");
  lcd.print(bufff);

  lcd.setCursor(0,2); //Τοποθέτησε τον κέρσορα στην τρίτη γραμμή και πρώτη στήλη στην οθόνη LCD

  
  
  if ((now.hour()==17) && (now.minute()==00) && (now.second()==00)){
    lcd.setCursor(0,2);
    lcd.print("EISERXESTE");
    digitalWrite(relay, HIGH);
    delay(5000);
    digitalWrite(relay, LOW);
    lcd.setCursor(0,2);
    lcd.print("                ");
  }  
   if ((now.hour()==18) && (now.minute()==15) && (now.second()==00)){
    lcd.setCursor(0,2);
    lcd.print("EKSERXESTE");
    digitalWrite(relay, HIGH);
    delay(10000);
    digitalWrite(relay, LOW);
    lcd.setCursor(0,2);
    lcd.print("                ");
  }  

     if ((now.hour()==18) && (now.minute()==30) && (now.second()==00)){
      lcd.setCursor(0,2);
    lcd.print("EISERXESTE");
    digitalWrite(relay, HIGH);
    delay(10000);
    digitalWrite(relay, LOW);
    lcd.setCursor(0,2);
    lcd.print("                ");
  }  
   if ((now.hour()==19) && (now.minute()==10) && (now.second()==00)){
    lcd.setCursor(0,2);
    lcd.print("ALLAGI");
    digitalWrite(relay, HIGH);
    delay(4000);
    digitalWrite(relay, LOW);
    lcd.setCursor(0,2);
    lcd.print("                ");

   }

    if ((now.hour()==20) && (now.minute()==20) && (now.second()==00)){
    lcd.setCursor(0,2);
    lcd.print("OPOU FYGEI FYGEI");
    digitalWrite(relay, HIGH);
    delay(10000);
    digitalWrite(relay, LOW);
    lcd.setCursor(0,2);
    lcd.print("                ");

   }


  
}


