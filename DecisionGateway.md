#This page explains what decision gateways in IBM BPM are.


[Back to Table of Contents](TableOfContents.md)



# Decision Gateway #
  * Decision gateways in IBM Process Designer are used to direct the flow of tokens through an instance of a BPD.

  * The decision gateway(switch gateway) is used to route the execution path of the service based on the evaluation of an expression.

  * Switch gateways provide a point where the run-time process may "select" one of a number of paths depending on some variable input, either from an end user or other run-time component.

  * Switches are a way to stack multiple conditions together to enable the process to switch among different tracks.

  * All the operation in a Switch gateway operates behind the scenes and is not visible to the run-time user.


# General Rules #
  * If all conditions that you wrote are evaluated to False, the process proceeds along the Default sequence line (by default, the Default sequence line is the first line that you created on the Switch).

  * When the first possible condition evaluates to True, the Token is created on that sequence line and the remaining sequence lines are ignored.

  * When you work with variables in conditions, remember that the SINGLE equals sign (=) means assignment in JAVASCRIPT and not comparison. And most of the work in a Switch gateway is accomplished with comparison and logical operators.


# Decision Gateway Patterns #
Basic information about the different kinds of gateways are given below:

## Exclusive Gateway ##
  * This kind of gateway sends tokens along only one of several possible paths based on a specific condition.
  * There must be at least 2 outgoing paths, but there is no upper limit.
  * This kind of gateway allows one token in and one token out; the gateway evaluates one condition at a time and once one of them is met, the token is passed onto the corresponding path and the rest of the conditions are not evaluated.
  * If no conditions are met, the token is sent along the "default" flow line.
  * It is good practice to ensure that only one condition can be met.

## Inclusive Gateway ##
  * This kind of gateway can function as a split (i.e. multiple tokens can be generated from one and sent along diverging flow lines) and a join (multiple tokens can be consolidated into one).
  * For inclusive split gateways, a token enters and is evaluated according to one or more conditions.
  * Unlike exclusive gateways, ALL conditions are evaluated.  If more than one condition is met, multiple tokens are generated and sent along the corresponding flow lines.  If none of the conditions are met, a token is sent along the default flow line.
  * For inclusive join gateways, the gateway "looks" upstream and waits for ALL tokens to arrive, then CONSOLIDATES them into a single token and sends them along the path.
  * An inclusive gateway can also have multiple lines in and multiple lines out, in which case, all tokens are consolidated into one, which then undergoes evaluation as if it entered a normal inclusive split.

## Parallel Gateway ##
  * These gateways can also act as splits and joins.
  * Unlike exclusive and inclusive gateways, parallel splits have NO conditions at all.
  * They direct a token along each and every possible flow line; there is no default flow line, since ALL flow lines are utilized.
  * Parallel joins wait for a token from every INCOMING flow line before consolidating the tokens and passing them onto the outgoing flow.
  * Only use a parallel join if you are certain that a token will flow along each incoming flow line every time.

## Event Gateway ##
  * These gateways wait for one (or more) message events or timer events to determine the flow through the gateway.
  * These events are boxed together with the gateway to show that they function together.
  * Although many paths can originate from the gateway, only one path will be taken. This path is based solely on the event that occurs within the gateway. Tokens from multiple instances can be allowed into the gateway at once, but these instances will be evaluated separately from one another.


## Note ##
  * Exclusive gateway is the default gateway provided in BPM.
  * All the assignments and projects are to be modeled using 'Exclusive Gateways'.

## Sample screenshot of Exclusive Decision gateway ##
![http://i.imgur.com/9bJh8jm.jpg](http://i.imgur.com/9bJh8jm.jpg)


## Tutorial ##
[Tutorial: Decision Gateway](Tutorial_DecisionGateway.md)