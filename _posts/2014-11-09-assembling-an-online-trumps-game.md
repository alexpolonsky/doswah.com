---
layout: post
title: "Let's Talk Trumps"
modified: 2014-11-09 17:08:28 -1000
description: "Re-creating the classic card game."
category: [Coding]
tags: []
image:
  feature: 
  credit: 
  creditlink: 
comments: true
share: 
---

Starting in my high school days and going through my college years, I played a card game 
so invigorating where cleverness and wit are needed to stand
victorious at the end. No, not *Magic: The Gathering*. I'm talking about **Trumps**.
<br><br>
Creating an online trumps game would allow my
college buddies and I to play the game we spent hours playing in between homework breaks.
Back then, we played to get away from the work. If this game came to fruition, it can
become a way for people to come together, no matter where they are in the world (as long
as they have Wi-Fi).

## The Setup / Pre-Game

To picture what a trumps game would look like, this post is  to lay down the basis of the game's
rules and flowchart to clarify any inconsistencies (since the game has spawned unique 
rules over the years).

<figure>
	<img src="/images/trumps/trumps-deal.png">
	<figcaption>Typical deal setup for Trumps</figcaption>
</figure>

The game consists of a 4-player, 2 vs. 2 system. In the figure above, Hands **A** & **C** are 
teammates and vice-versa, Hands **B** & **D** are teammates. With 52 cards in a deck, each lettered
player is dealt 12 cards and 4 cards are placed at the center of the table called the *Kit* 
(12+12+12+12+4=52).

### Bidding War

Once the hands are dealt, *the player **left** of the dealer makes a "bid" to 1) win the kit 
2) declare what suit trumps is and 3) Designate how many packs the other team must make to win*. 
Each player has the chance to bid with the dealer getting to bid last. A player can overbid 
the previous bid by bidding a higher number. 

<br>

In accordance to the bidding number, each bid is either **LOW** or **HIGH**. A **LOW** bid declares 
lower valued cards in a suit are stronger in the game, while vice-versa, a **HIGH** bid declares 
higher valued cards in a suit are stronger. In all games, the ACE card 
is the strongest card of the suit. In the following table, the higher the card is in the table, 
the stronger it is during the game.

<table rules="groups">
  <thead>
    <tr>
      <th style="text-align: center">When LOW bid wins</th>
      <th style="text-align: center">When HIGH bid wins</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">ACE</td>
      <td style="text-align: center">ACE</td>
    </tr>
    <tr>
      <td style="text-align: center">2</td>
      <td style="text-align: center">KING</td>
    </tr>
    <tr>
      <td style="text-align: center">3</td>
      <td style="text-align: center">QUEEN</td>
    </tr>
    <tr>
      <td style="text-align: center">3</td>
      <td style="text-align: center">JACK</td>
    </tr>
    <tr>
      <td style="text-align: center">4</td>
      <td style="text-align: center">10</td>
    </tr>
    <tr>
      <td style="text-align: center">5</td>
      <td style="text-align: center">9</td>
    </tr>
    <tr>
      <td style="text-align: center">6</td>
      <td style="text-align: center">8</td>
    </tr>
     <tr>
      <td style="text-align: center">.</td>
      <td style="text-align: center">.</td>
    </tr>
    <tr>
      <td style="text-align: center">.</td>
      <td style="text-align: center">.</td>
    </tr>
    <tr>
      <td style="text-align: center">.</td>
      <td style="text-align: center">.</td>
    </tr>
  </tbody>
</table>

<br>

*It's important to note: a LOW bid over-rules a HIGH bid.* For example, consider Player A starts 
the bidding at *4 HIGH*. If the following player bids *4 LOW*, then
he or she now holds the current winning bid.

<br>

As I mentioned earlier, the winning bid determines how much packs the other 
team needs to make to win the game. Here is what each bidding number represents.

**Packs** are considered as a round where all four players contribute a card in play. Since 
each player has 12-cards, there are 12 rounds or "packs".
{: .notice}

<table rules="groups">
  <thead>
    <tr>
      <th style="text-align: center">Winning Bid</th>
      <th style="text-align: center"># of Packs Other Team Needs To Win</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">1</td>
      <td style="text-align: center">7</td>
    </tr>
    <tr>
      <td style="text-align: center">2</td>
      <td style="text-align: center">6</td>
    </tr>
    <tr>
      <td style="text-align: center">3</td>
      <td style="text-align: center">5</td>
    </tr>
    <tr>
      <td style="text-align: center">4</td>
      <td style="text-align: center">4</td>
    </tr>
    <tr>
      <td style="text-align: center">5</td>
      <td style="text-align: center">3</td>
    </tr>
    <tr>
      <td style="text-align: center">6</td>
      <td style="text-align: center">2</td>
    </tr>
    <tr>
      <td style="text-align: center">7</td>
      <td style="text-align: center">1</td>
    </tr>
  </tbody>
</table>

<br>
Once a player wins the bid he or she uses the "Kit" to add/remove cards to improve their 
12-card hand. Once that's done, the player declares what "trumps" is and then the game
begins.

## How Trumps Works

I explained the quite troublesome setup for a trumps game, but now we to get into the fun. 
<br><br>
Each round, a player adds one card to the pile and person who adds the strongest card wins a 
pack for their team. When a person wins a pack for their team, they become the person 
who throws first for the next round. Now introducing trumps. "Trumps" represent the **suit** that 
overpowers cards from the other three suits. 
<br><br>
In a game, the player who throws first declares the suit "in play". Each player must throw 
the suit in play. When a person does not have the suit in play, they can 
throw a trump, to better their chances to win the pack. According to the rules, the trump suit cannot 
be used to start a round unless previous scenario occurs (due to lack of "in play" suit in someone's hand). This is commonly referred to as "Breaking Trumps".
<br><br>
Those are the basic rules of Trumps. Let's examine a few rounds.

## An Example Game of Trumps 

The great Christian Damo ([@HenryHanakahi](https://twitter.com/HenryHanakahi)) taught me 
that introducing a scenario is a productive way to explain people new things. So let's consider
this scenario.

* Players A & C are a team (so, players B & D are a team).
* Player C wins the bid at **4 LOW**
* Player C declares trumps as **SPADES**

*Images for card faces in the following scenarios are provided by [was.fm](http://was.fm/assets:textures:playing_cards)*.

<br>

Now since player C won the bid, he starts the game of by throwing a suit. This is what happens...

1. Player C throws 4 of HEARTS
2. Player D throws 6 of HEARTS
3. Player A throws 9 of HEARTS
4. Player B throws 2 of HEARTS

<figure>
	<img src="/images/trumps/trumps-hand-1.png">
</figure>

Player C throws and declares HEARTS as the suit in play. Player D could not beat the 4 of HEARTS so he throws any heart, in this scenario he throws the 6 of HEARTS. 
Next Player A throws a 9 of HEARTS because heassumes the 4 of HEARTS his partner threw will win. 
Now Player B throws the 2 of HEARTS, resulting in his team winning a pack. Just a taste of how rough this game can be. Since Player B won, he will start the next round.

1. Player B throws 7 of DIAMONDS
2. Player C throws ACE of DIAMONDS
3. Player D throws 10 of SPADES
4. Player A throws 9 of DIAMONDS

<figure>
	<img src="/images/trumps/trumps-hand-2.png">
</figure>

Player B declares DIAMONDS as the suit in play. Player C attempts to win the hand by playing the ACE of DIAMONDS (the strongest number of a suit). It appears 
Player D does not have any DIAMONDS in his hand so Player D is entitled to throw a "trump" card. 
Like I mentioned earlier, the trumps suit overpowers any of the other three suits. So although 
Player C threw an ACE, Player D's 10 of SPADES is stronger since it is a "trump". Unfortunately for 
Player A, he cannot throw a trump to beat Player D's 10 of SPADES because he or she still has DIAMONDS. 
As a reminder since the first player, Player B, started out with a DIAMOND, everyone must throw a 
DIAMOND unless they don't have any.

<br>

This has been a basic introduction into how the game of trumps works. Next post I plan introduce 
how to organize a card deck in a coding viewpoint using classes. Also I will discuss the language and 
technology stack I could use for the game. I am at an early stage and have a lot to plan and 
research. Until next time.
