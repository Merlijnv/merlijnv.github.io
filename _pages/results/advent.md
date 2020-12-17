# Advent ctf

In the december month there was a really interesting ctf advent calendar.
I started later on in the advent calendar on day 7.
On my first day I did challenge 0-4.
Here I discuss some advents that I tought was interesting.

- [Advent ctf](#advent-ctf)
  * [Challenge 0](#challenge-0)
  * [Challenge 1](#challenge-1)
  * [Challenge 3](#challenge-3)
  * [Challenge 4](#challenge-4)
  * [Challenge 8](#challenge-8)


## Challenge 0
![Challenge 0](/images/challenge0.png)
The teaser site huh after looking for a teaser site I tried way back machine.
There was 1 other date in the way back machine.
In the code, there was encryption.

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

## Challenge 3
This challenge had a login but the login used javascript it takes the username and adds -NOVI to it and then base64 encrypts it. Then the result of that it compares to the password.
So I had to for example use a as username and base64 encrypt a-NOVI and that's the password.

## Challenge 4
I started with a login after inserting random username and password I got a response site but I couldn't go back after looking into the cookies I found a token.
I decrypted it with cyber chef and got a json with guest true admin false. I changed it to guest false admin true. That didn't work there was a second part to it. It looked like a key so I changed it to user 1-5 and calculated the key when I got to user 5 it worked.
![challenge 4](/images/challenge4.png)


## Challenge 8
![challenge 8](/images/challenge8.png)
At the beginning this was a really confusing challenge this was a really empty page without any interesting in the code.

![challenge 8 robots.txt](/images/challenge8robots.png)
Here we find 2 interesting pages 1 has a rhyme but a really weird url.
The other has a encrypted message.
![challenge 8 encrypted](/images/challenge8encrypted.png)
After I found out it's base64 encoded it says: "Encoding and encryption are 2 different things."

After some thinking I thought the weird url could maybe be rot13.
After decoding it says "/santa/has/many/places/to/go" when going to this url we got the flag
