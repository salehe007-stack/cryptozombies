# cryptozombies- lesson 1

This repo is where I'm keeping my work as I go through the CryptoZombies course to learn Solidity and smart contract development. This is Lesson 1: the Zombie Factory.

## What this is

CryptoZombies teaches Solidity by getting you to build a zombie game on Ethereum one small step at a time. Lesson 1 builds a smart contract that can create a zombie with random DNA and keep a permanent record of every zombie ever made.

## What the contract does

When someone calls it with a name, it turns that name into a random 16-digit DNA number using a hash function, creates a zombie (a name paired with its DNA) and saves it to a list stored on the blockchain, works out the new zombie's id (its position in that list), and then fires an event to announce that a new zombie was born, so a front-end app could listen and display it.

## What I learned

A lot of this was new to me. Some of the things that finally clicked: how a function is put together (its name, inputs, whether it's public or private, and what it gives back), why you'd keep internal helper functions private, data locations like memory and why some types need them, and how storing a value works — that = means "put the right side into the left side", not "equals" like in maths.

I also got my head around hashing with keccak256 and packing data with abi.encodePacked to make the random DNA, typecasting between number types, how arrays work (push gives you back the new length, so length minus 1 is the position of the item you just added), and what events are for — how a contract announces things to the outside world.

## The tricky bit

The part that took me longest was the nested code — a function call wrapped inside another wrapped inside a typecast, with all the parentheses. What made it click was building it from the inside out, one layer at a time, and counting the brackets so every open had a close.

## Next

On to Lesson 2.
