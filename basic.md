Shared: public  number x
Bob:    private number y
Alice:  private number z

Send: number x...

Bob:   x+y = b
Alice: x+z = a

Send: b ...
Send: a ...

Bob:   a+y = common number
Alice: b+z = common number 

because x + y + z = x + z + y
but this is easy to reverse ... so let's instead use something very difficult to reverse...

modulus should be a big prime number
the base needs to produce as many possible remainder values as possible (i.e. 1 is a poor choice)
 - with a mod of 19, choosing 4 as a base is still a bad idea as it does not generate all possible remainders of mod 19
 + 3 is a much better choice

int algo(int base, int power, int mod) {
	return (base ^ power) % mod;
}

public number base
public number mod
Bob:   number y
Alice: number z

Send public numbers: base, mod ...

Bob:   algo(base, y, mod) = b
Alice: algo(base, z, mod) = a

Send b ...
Send a ...

Bob:   algo(a, y, mod) = shared number
Alice: algo(b, z, mod) = shared number

credit: https://www.youtube.com/watch?v=85oMrKd8afY&ab_channel=SpanningTree
