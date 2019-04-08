# Bitcoin High-Value Custody Plan Using Electrum Multisig

The plan offers protection from the following threats:

* Computer getting hacked
* Being robbed at gunpoint
* One or more copies of keys being lost
* Funds becoming inaccessible to heirs due to your death

I'll share the plan below. Please poke holes at it so we can improve it.

The plan uses 2-of-3 multisig HD wallet. It maintains your full sovereignty. But it also puts some distance between you and direct access to the funds. This is to thwart in-person attacks.

Here we go...

## Generate and store your keys

Get a brand-new offline-only laptop. Install Electrum on the laptop (using a USB stick). Don't install anything else. Using this offline laptop, generate three seeds and their corresponding master public keys:

* Seed A
* Master public key A
* Seed B
* Master public key B
* Seed C
* Master public key C

Create copies of seeds A and B and master public keys A and B, so that you have the following:

* Seed A copy 1
* Seed A copy 2
* Seed B copy 1
* Master public key A copy 1
* Master public key A copy 2
* Master public key A copy 3
* Master public key B copy 1
* Master public key B copy 2
* Master public key B copy 3
* Master public key C copy 1
* Master public key C copy 2
* Master public key C copy 3

(Notice that we haven't created any copies for seed C. We'll get to seed C in a bit.)

Now group your copies as follows:

* Group 1:
  * Seed A copy 1
  * Master public key A copy 1
  * Master public key B copy 1
  * Master public key C copy 1
* Group 2:
  * Seed A copy 2
  * Master public key A copy 2
  * Master public key B copy 2
  * Master public key C copy 2
* Group 3:
  * Seed B copy 1
  * Master public key A copy 3
  * Master public key B copy 3
  * Master public key C copy 3
  
Give group 1 and 2 to two different people you trust. Put group 3 in a safe deposit box. As for seed C, store it on your phone, locked by a memorizeable brain-password and backed up to an online cloud.

Delete your wallet from the offline laptop. 

Losing this offline laptop should not compromise your funds. But to protect against malware/spyware and to ensure that this laptop stays offline, don't let anyone access it. If you suspect someone had access to it, get another one.

## How to spend

Get another brand-new online laptop. Configure it to connect to the Internet through TOR only. Don't install anything on it. Don't even open a web browser. Using a USB stick, install Electrum. Create a watch-only wallet on this laptop using your master public keys A, B, and C.

Create a transaction on the online laptop. Scan its QR code and keep the QR code on your phone to later import to the _offline laptop_.

You have seed C on your phone. Now acquire seed A and master public key B or acquire seed B and master public key A. You can acquire seed A from one of its holders or acquire seed B from the safe deposit box. You can acquire the master public keys from any location where you have one of your seeds. 

Using two seeds and one master public key, restore your wallet on the offline laptop.

Import the transaction from your phone to the offline laptop and sign it. Scan the _signed_ transaction's QR code and keep the QR code on your phone to later import into the _online laptop_. 

Delete your wallet from the offline laptop.

Import the signed transaction to the online laptop. Broadcast transaction.

## How to receive

Everytime you want to receive, generate an address using the watch-only online laptop. Display the address as a QR code. Scan it with your phone. Then share it.

## How you're protected

### Computer getting hacked

Very little chance of your online laptop getting hacked since there's nothing on it but Electrum. Even if it gets hacked, the worst that can happen is that your wallet becomes trackable but your funds are still secure because your online wallet has your public keys but not your seeds.

Your offline laptop should never get hacked because it never connects to the internet.

### Being robbed at gunpoint

To be able to transfer funds to the robber, you need seed A or B in addition to seed C. You can't get access to seed A or B without talking to at least one other person.

This is risky for the robber because he would have to wait for you acquire seed A or B. The actions needed to acquire seed A or B could result in authorities being alerted. These actions prolong the robbery and give the authorities more time to react. A robber is more likely to call off the attack at this point.

### One key being lost

You need 2 of 3 keys. You have backups of each of the 3 keys and each of the master public keys. There is very little chance of losing access to funds due to key loss.

### Funds becoming inaccessible to heirs due to your death

You want your heirs to be able to access your funds when you die.

Your heirs can be seed A holders. If they're not, then they can contact seed A holders. They can prove your death and access your safe deposit box. Now they have enough information to unlock and retrieve your estate.

Additionally, if you manage your digital life correctly, they may be able to retrieve seed C.

## Additional protections

### Collusion of seed A holders

Seed A holders cannot collude because they have copies of the same key. 

### Banks or safe deposit box business withholding access

That would not be a problem because you can use seed A instead of seed B.

## Unmitigated or new threats due to this plan

This plan is pretty good but it's still not completely without flaws:

### Forgetting to delete the wallet from offline laptop

There's a chance that you may forget to delete the wallet from the offline laptop. If in that case someone gets physical access to your offline laptop, you will lose your funds.

It would be great if Electrum offered the option to not create a wallet file. Such an option would improve this plan.

### Hard disk data recovery

Electrum stores wallet file on disk. Even if you delete the wallet, it can be retrieved using data recovery techniques.(?)

### Robber forces you to make a phone call to a seed A holder

A very reckless robber might be willing to have you phone another person to receive seed A and send the funds. 

To protect against this threat, you could store seed A in a safe deposit box in a different country. Doing that would increase resiliency to catastrophic political or natural events in one country.
