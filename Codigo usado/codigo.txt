const byte N1 = 5; 

const byte N2 = 4; 

const byte N3 = 3; 

const byte N4 = 2; 

void setup() { 

  Serial.begin(9600); 

  for (byte pin = 2; pin < 6; pin++) { 

    pinMode(pin, OUTPUT); 

  } 

} 

void loop() { 

   

  if (Serial.available() > 0) { 

     

    char comando = Serial.read(); 

    Serial.println(comando); 

     

    if (comando == 'w') {       //Comando tanque para frente 

      direcao(0, 1, 0, 1);      //Chamada da função direção N1=0, N2=1, N3=0, N4=1    

    } 

    else if (comando == 'q') {  //Comando tanque parado 

      direcao(0, 0, 0, 0);      //Chamada da função direção N1=0, N2=0, N3=0, N4=0 

    } 

    else if (comando == 's') {  //Comando tanque ré 

      direcao(1, 0, 1, 0);      //Chamada da função direção N1=1, N2=0, N3=1, N4=0 

    } 

    else if (comando == 'd') {  //Comando tanque para direita 

      direcao(0, 1, 1, 0);      //Chamada da função direção N1=0, N2=1, N3=1, N4=0     

    } 

    else if (comando == 'a') {  //Comando tanque para esquerda 

     direcao(1, 0, 0, 1);      //Chamada da função direção N1=1, N2=0, N3=0, N4=1    

    } 

  } 

} 

void direcao(byte N1, byte N2, byte N3, byte N4) { 

  digitalWrite(11, N1); //Motor Esquerdo 

  digitalWrite(6, N2); 

  digitalWrite(7, N3);  //Motor Direito 

  digitalWrite(8, N4); 

} 

 