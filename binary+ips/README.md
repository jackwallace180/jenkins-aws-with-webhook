# Binary and IP Adresses :key: :taco: :key: #

## :interrobang: Binary :zero::one::zero::one: ##

Binary uses a base 2 system, so each digit represents the next power of 2 (compared to our normal number system which is base 10 so every new digit represents the next power of 10). This means in binary each digit can only be 0 or 1. so the first digit in a binary number represents 2^0 and the second digit 2^1, 3rd digit 2^2 etc. Again compared to our number system which digits is 10^0, 10^1, 10^2 etc. Below is a binary table for the first 8 digits (this will be able to make any number up to 255)

| 128  | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
|  0 or 1  | 0 or 1   | 0 or 1   |   0 or 1 |  0 or 1  | 0 or 1   |0 or 1    |0 or 1    |

An example we shall use here is the number 198, to change this into binary first start from the left of this table and see if 128 will go into it. 128 does go into 198 so we put a 1 in that column. We then have 70 left over, so next we look at the 64 column, 64 does go into 70 so again we put a 1. We now have 6 left over and go to the next column which is 32, 32 does not go into 6 so we put a 0. Next column is 16 which again does not go into 6 so we put a 0 in that column, the same for the 8 column. Then we get to the 4 column, 4 does go into 6 so we put a 1 and have 2 left over. The next column is 2, and 2 does go into 2 so we put a 1 and have 0 left over, the last column is 1 but 1 does not go into 0 so we put a 0. Our table for 198 will look like this:

| 128  | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
|  1  | 1   | 0   |   0 |  0  | 1   |1    |0 |

Just for clarity a base 10 table (the system we use for numbers normally) for 198 would look like this:

| 1000 | 100 | 10 | 1 |
| ------------- | ------------- | ------------- | ------------- |
|  0  | 1   | 9  |8 |

## :globe_with_meridians: :milky_way: IP addresses :signal_strength: ##

IPv4 use 8 bit binary for the four numbers in the address. This means there are 8 numbers (the same system we used in the binary table above!) that can be 1 or 0 as seen below!

![binary](https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Ipv4_address.svg/300px-Ipv4_address.svg.png)

An easy was to find you  IP address is to type in "ipconfig" into gitbash! This will also show you your subnet mask which we will talk about next.

## :mask: :beers: Submask and CIDR :beers: :mask: ##

### Submask ###

Submasks look like IP addresses but are used to see if other addresses can communicate with eachother. If you write out the submask in binary you will get a bunch of 1's and 0's. Whenever there is a 1 the IP addresses must be the same in order for them to communicate with eachother.

an example submask would be 255.255.192.0 which translates into binary as

 - 11111111.11111111.11000000.00000000

 since the first 18 digits are all 1s the first 18 digits of the 2 IPs MUST match!

 so if you have IP1 = 192.96.8.10 and IP2 = 192.96.4.12 they would be represented like this:

 - 11000000.01100000.00001000.00001010
 - 11000000.01100000.00000100.00001100

Which as we can see the first 18 digits match! so these IPs can communicate through the submask! the last 14 digits are different but this does not matter as our submask has 14 0's at the end meaning they dont have to match.

### CIDR blocks ###

Often when you see IPs they will have a " / " and a number (often 8,16,24 or 32). This is known as the CIDR block. CIDR blocks count how many 1's come up in a row from the LHS in a submask. So using our example from earlier our submask has 18 1's in a row which means our CIDR block for this submask would be /18. So we can write our IP addresses like 192.96.8.10/18. So now we know if any IP address has the same first 18 binary digits as our IP address they can communicate.

CIDR blocks are VERY regularly written as /8 /16 /24 /32. /8 means that the first number of an IP has to be exactly the same, which would be representing the submask 255.0.0.0. This is nice as we dont even have to convert to binary which is a tedious task. /16 would mean the first 2 numbers in the IP are the same (255.255.0.0) and so on.

So if we see an IP address such as 200.210.64.12/16 we know that any IP that starts with 200.210... will be able to communicate with it.
