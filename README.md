# biginteger-cpp

Big integer class in c++ (coded with competitive programming problems in mind)

## Prototypes

```c++
BigInt(string x);
BigInt(int x);
BigInt negative();
BigInt normalize(int newSign);
void operator =(string x);
bool operator ==(const BigInt &x) const;
bool operator <(const BigInt &x) const;
bool operator <=(const BigInt &x) const;
bool operator >(const BigInt &x) const;
bool operator >=(const BigInt &x) const;
BigInt operator +(BigInt x);
BigInt operator -(BigInt x);
BigInt operator *(BigInt x);
BigInt operator /(BigInt x);
BigInt operator %(BigInt x);
string toString() const;
BigInt toBase10(int base);
BigInt toBase10(int base, BigInt mod);
string convertToBase(int base);
friend ostream &operator <<(ostream &os, const BigInt &x);
```

## Example
### Compute ```num % mod``` in base 19
```c++
int base = 19;
string num, mod;

cin >> num >> mod;

BigInt base10Mod = BigInt(mod).toBase10(base);  // convert to base 10 from base 'base'
BigInt base10Num = BigInt(num).toBase10(base, base10Mod); // convert to base 10 (and modulo 'base10Mod')

cout << (base10Num % base10Mod).toBase(base) << "\n"; // get the modulo and convert it back to base 'base'
```
