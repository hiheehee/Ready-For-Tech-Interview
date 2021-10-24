# 최대공약수 GCD : Greatest Common Divisor
* 두 자연수의 공통된 약수 중 가장 큰 수
 
# 최소공배수 LCM : Least Common Multiple
* 두 자연수의 공통된 배수 중 가장 작은 수
* 최소공배수 = 두 자연수의 곱 / 최대공약수

```java
// 최대 공약수 
static int GCD(int a, int b) { 
   while(b > 0) { 
       int temp = a; 
       a = b; 
       b = temp%b; 
   } 
   return a; 
 }
 
 // 최소 공배수 
 // a*b할때 int 범위 초과할 수 있으니 유의해야 한다. 
 static int LCM(int a, int b) { 
     return (a*b)/GCD(a, b); 
 }
 ```
