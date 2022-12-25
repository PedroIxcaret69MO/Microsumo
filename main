//drv833 pins
int in1 = 3;
int in2 = 5;
int in3 = 6;
int in4 = 9;
//sensors, button and start module
int s4 = A1;
const int s1 = 10;//right
const int s2 = 8;//mid
const int s3 = 7;//left
const int but = 4;
const int arr = 2;
//states of sensors, button and start module
int sts1; 
int sts2; 
int sts3; 
int sts4;
int stb; 
int sta;

void setup() 
{
  pinMode(in1,OUTPUT);
  pinMode(in2,OUTPUT);
  pinMode(in3,OUTPUT);
  pinMode(in4,OUTPUT);
  pinMode(s1,INPUT);
  pinMode(s2,INPUT);
  pinMode(s3,INPUT);
  pinMode(s4,INPUT);
  pinMode(but,INPUT);
  pinMode(arr,INPUT);
}

void loop() 
{
  stb = digitalRead(but); 
  sta = digitalRead(arr);

  while (sta == LOW) sta = digitalRead(arr);
  while(sta == HIGH)
  {
    for(int i=0; i<180000; i++)
    {
      sts1 = digitalRead(s1);
      sts2 = digitalRead(s2);
      sts3 = digitalRead(s3);
      sts4 = analogRead(s4);
      if(sts4 <= 60)
      {
        move();
      }else{atacar();}
      sta = digitalRead(arr);
      if(sta==LOW)break;
      delay(1);
    }
  }
  stop();
}

void atacar()
{
  if ((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == HIGH))
  {
    forwards(50);
  }
  else
  {
    if (((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == LOW)) || ((sts1 == HIGH) && (sts2 == LOW) && (sts3 == LOW)))
    {
      left(255);
    }
    else
    {
      if (((sts1 == HIGH) && (sts2 == LOW) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == LOW)) || ((sts1 == LOW) && (sts2 == HIGH) && (sts3 == LOW)))
      {
        forwards(255);
      }
      else
      {
        if (((sts1 == LOW) && (sts2 == HIGH) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == HIGH))) 
        {
          right(255);
        }
      }
    }
  }
}

void handR()
{
  if ((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == HIGH))
  {
    right(150);
  }
  else
  {
    if (((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == LOW)) || ((sts1 == HIGH) && (sts2 == LOW) && (sts3 == LOW)))
    {
      left(255);
    }
    else
    {
      if (((sts1 == HIGH) && (sts2 == LOW) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == LOW)) || ((sts1 == LOW) && (sts2 == HIGH) && (sts3 == LOW)))
      {
        forwards(255);
      }
      else
      {
        if (((sts1 == LOW) && (sts2 == HIGH) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == HIGH))) 
        {
          right(255);
        }
      }
    }
  }
}

void handL()
{
  if ((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == HIGH))
  {
    left(150);
  }
  else
  {
    if (((sts1 == HIGH) && (sts2 == HIGH) && (sts3 == LOW)) || ((sts1 == HIGH) && (sts2 == LOW) && (sts3 == LOW)))
    {
      left(255);
    }
    else
    {
      if (((sts1 == HIGH) && (sts2 == LOW) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == LOW)) || ((sts1 == LOW) && (sts2 == HIGH) && (sts3 == LOW)))
      {
        forwards(255);
      }
      else
      {
        if (((sts1 == LOW) && (sts2 == HIGH) && (sts3 == HIGH)) || ((sts1 == LOW) && (sts2 == LOW) && (sts3 == HIGH))) 
        {
          right(255);
        }
      }
    }
  }
}

void move()
{
  backwards(255);
  delay(300);
  right(255);
  delay(300);
}

void backwards(int pwmb)
{
  analogWrite(in1,0);//right
  analogWrite(in2,pwmb);
  analogWrite(in3,0);//left
  analogWrite(in4,pwmb);
}

void forwards(int pwmf)
{
  analogWrite(in1,pwmf);//right
  analogWrite(in2,0);
  analogWrite(in3,pwmf);//left
  analogWrite(in4,0);
}

void left(int pwml)
{
  analogWrite(in1,pwml);//right
  analogWrite(in2,0);
  analogWrite(in3,0);//left
  analogWrite(in4,pwml);
}

void right(int pwmr)
{
  analogWrite(in1,0);//right
  analogWrite(in2,pwmr);
  analogWrite(in3,pwmr);//left
  analogWrite(in4,0);
}

void stop()
{
  analogWrite(in1,0);//right
  analogWrite(in2,0);
  analogWrite(in3,0);//left
  analogWrite(in4,0);
}
