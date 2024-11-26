# infoless_60
**ВОПРОС:1. Функция для вычисления максимального из трёх чисел:**

```
function MaxOfThree(a, b, c: Integer): Integer;
begin
    if (a >= b) and (a >= c) then
        MaxOfThree := a
    else if (b >= a) and (b >= c) then
        MaxOfThree := b
    else
        MaxOfThree := c;
end;
```

**ВОПРОС:2. Функция для вычисления максимального и минимального из трёх чисел:**

```
procedure MinMaxOfThree(a, b, c: Integer; var min, max: Integer);
begin
    min := a;
    max := a;
    
    if b < min then
        min := b;
    if c < min then
        min := c;

    if b > max then
        max := b;
    if c > max then
        max := c;
end;
```

ВОПРОС:3. Функция для вычисления количества цифр числа:

```
function CountDigits(n: Integer): Integer;
var
    count: Integer;
begin
    count := 0;
    
    while n <> 0 do
    begin
        n := n div 10;
        count := count + 1;
    end;
    
    CountDigits := count;
end;
```

**ВОПРОС:4. Функция для вычисления наибольшего общего делителя:**

```
function GCD(a, b: Integer): Integer;
begin
    while b <> 0 do
    begin
        GCD := b;
        b := a mod b;
        a := GCD;
    end;
    GCD := a;
end;
```

**ВОПРОС:5. Функция для вычисления наименьшего общего кратного:**

```
function LCM(a, b: Integer): Integer;
begin
    LCM := (a * b) div GCD(a, b);
end;
```

**ВОПРОС:6. Функция, которая «разворачивает» десятичную запись числа:**

```
function ReverseNumber(n: Integer): Integer;
var
    reversed: Integer;
begin
    reversed := 0;
    while n <> 0 do
    begin
        reversed := reversed * 10 + (n mod 10);
        n := n div 10;
    end;
    ReverseNumber := reversed;
end;
```

**ВОПРОС:7. Функция моделирования бросания двух игральных кубиков:**

```
function RollDice: Integer;
begin
    Randomize;
    RollDice := Random(6) + 1 + (Random(6) + 1);
end;
```

**ВОПРОС:8. Функция для вычисления факториала:**

```
function Factorial(n: Integer): Integer;
begin
    if n = 0 then
        Factorial := 1
    else
        Factorial := n * Factorial(n - 1);
end;
```

**ВОПРОС:9. Функция для вычисления N-го числа Фибоначчи:**

```
function Fibonacci(n: Integer): Integer;
begin
    if n <= 1 then
        Fibonacci := n
    else
        Fibonacci := Fibonacci(n - 1) + Fibonacci(n - 2);
end;
```

**ВОПРОС:10. Функция для нахождения дружественных чисел:**

```
function SumOfDivisors(n: Integer): Integer;
var
    sum, i: Integer;
begin
    sum := 0;
    for i := 1 to n div 2 do
    begin
        if n mod i = 0 then
            sum := sum + i;
    end;
    SumOfDivisors := sum;
end;

procedure FindFriendlyNumbers(limit: Integer);
var
    i, sum1, sum2: Integer;
begin
    for i := 1 to limit do
    begin
        sum1 := SumOfDivisors(i);
        if (sum1 > i) and (sum1 <= limit then
        begin
            sum2 := SumOfDivisors(sum1);
            if sum2 = i then
                writeln(i, ' and ', sum1, ' are friendly numbers.');
        end;
    end;
end;
```

**ВОПРОС:11. Программа для нахождения чисел с постоянной суммой цифр:**

```
function DigitSum(n: Integer): Integer;
begin
    Result := 0;
    while n > 0 do
    begin
        Result := Result + n mod 10;
        n := n div 10;
    end;
end;

procedure FindNumbers(N: Integer);
var
    i: Integer;
    valid: Boolean;
begin
    for i := 0 to N do
    begin
        valid := True;
        for j := 2 to 9 do
        begin
            if DigitSum(i * j) <> DigitSum(i) then
            begin
                valid := False;
                Break;
            end;
        end;
        if valid then
            writeln(i);
    end;
end;
```

**ВОПРОС:12. Логическая функция для проверки совершенного числа:**

```
function IsPerfect(n: Integer): Boolean;
var
    sum, i: Integer;
begin
    sum := 0;
    for i := 1 to n div 2 do
    begin
        if n mod i = 0 then
            sum := sum + i;
    end;
    IsPerfect := (sum = n);
end;
```

**ВОПРОС:13. Логическая функция для проверки гиперпростого числа:**

```
function IsPrime(n: Integer): Boolean;
var
    i: Integer;
begin
    if n < 2 then
        Exit(False);
    for i := 2 to trunc(sqrt(n)) do
    begin
        if n mod i = 0 then
            Exit(False);
    end;
    IsPrime := True;
end;

function IsHyperprime(n: Integer): Boolean;
var
    s: String;
    i: Integer;
begin
    s := IntToStr(n);
    for i := 1 to Length(s) do
    begin
        if not IsPrime(StrToInt(Copy(s, 1, i))) then
            Exit(False);
    end;
    IsHyperprime := True;
end;
```


