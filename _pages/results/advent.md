# Advent ctf

In the december month there was a really interesting ctf advent calendar.
I started later on in the advent calendar on day 7.
On my first day I did challenge 0-4.

## Challenge 0
![Challenge 0](/images/challenge0.png)
The teaser site huh after looking for a teaser site I tried way back machine.
There was 1 other date in the way back machine.
In the code there was a encryption.

![waybackmachine](/images/waybackmachine.png)

After using cyber chef and letting it convert it from base64 I got the answer.

## Challenge 1
![Challenge 1](/images/challenge1site.png)
This time we need a password.
My first thought was would there be a hidden code in the html like challenge 0.
And there it was.
![Challenge 1 code](/images/challenge1code.png)
Again trying it in cyber chef and it works.
![challenge 1 solve](/images/challenge1solve.png)

## Challenge 2
//TODO

## Challenge 3
This challenge had a login but the login used javascript it takes the username and adds -NOVI to it and then base64 encrypts it. Then the result of that it compares to the password.
So I had to for example use a as username and base64 encrypt a-NOVI and that's the password.

## Challenge 4
I started with a login after inserting random username and password I got a response site but I couldn't go back after looking into the cookies I found a token.
I decrypted it with cyber chef and got a json with guest true admin false. I changed it to guest false admin true. That didn't work there was a second part to it. It looked like a key so I changed it to user 1-5 and calculated the key when I got to user 5 it worked.
![challenge 4](/images/challenge5.png)