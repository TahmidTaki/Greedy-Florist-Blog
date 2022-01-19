# Greedy-Florist-Blog
Hackerrank Greedy Florist problem

The problem is related to a greedy florist. usually when someone has repeating customer, seller should reduce the price. but as the florist is greedy he will charge more if someone buys more than 1 flower from him. 
for the first flower he will keep the original price which is (0+1)xoriginal price, for the next number of flowers he will twice, thrice the price of original meaning the price of (1+1)xoriginal price, (2+1)xoriginal price and so on. 

If there are a group of friends trying to buy a number of flowers, we need to minimize the total price withing with all the flowers can be bought. 

as the price increases after each purchase for a single friend, it would be better to buy the costly flowers first so that the price does not hike as much as buying cheap flowers at twice/thrice at rate.
to clarify: 2 flowers has price of 3, 7 respectively. 
if we buy 3 first at original price and 7 second at twice of its price then total is:
3+7*2=17
where as  if we buy 7 first at original price and 3 second at twice of its price then total is:
3*2+7=13

for this solution, we divide the most costly flowers to all the friends first at original price. after that, the lesser costly flowers are divided into all friends again at twice price. then the rest of the least costly flowers are divided to all friends at thrice the price and so on.

For visualizing purpose:
let us think there are 15 flowers of price 15,12,9,8,6,5,3,2,1,4,7,11,14,13,10 respectively. 
5 friends are supposed to buy them all.

First we sort the prices from high to low. as there are 5 friends, the highest valued 5 flowers will be bought by 5 friends at original price.

Then the those 5 friend will buy the flowers of price 10,9,8,7,6 at twice their price.

Then the those 5 friend will buy the flowers of price 5,4,3,2,1 at thrice their price.

In the code getminimumcost function:

line sort(c.begin(), c.end(),greater<int>()); -->is used to sort the prices
then price is set to 0 as nothing have been purchased yet and prev is set to 0 meaning no previous flower purchased.

After that we loop through and add the original price at first for all friends,
if(i==j) indicating all friends bought 1 flower each then we add 1 to prev, add number of friends k with j.

So for the example mentioned above:
Friend 1 will buy: 15, 10, 5
Friend 2 will buy: 14, 9, 4
Friend 3 will buy: 13, 8, 3
Friend 4 will buy: 12, 7,2
Friend 5 will buy: 11, 6, 1

