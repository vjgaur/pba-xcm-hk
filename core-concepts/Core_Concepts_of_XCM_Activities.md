## Exercises

Assume a setup where we have the relay chain, and two parachains with paraIds 1000 and 1001 respectively:

- Using XCM locations, how would you represent each of the following from the perspective of all three chains (relay, para1000, para1001)?

  - The relay chain

1.  Here
2.  ../Here
3.  ../Here

- Parachain 1000

1. Parachain (1000) - Here
2. Prachain(1001) - ../Parachain(1000)

- A 32 byte account in the relay

1. AccountId32
2. Parchain1000: ../AccountId32
3. Parchain1001: ../AccountId32

- A 20 byte smart contract address

1. Relay Parchain(1000)/AccountKey20(0X1010101010101001)
2. Parachain1000: Parchain(1000)/PalletiInstance(60)/AccountKey20(0X1010101010101001) // In case of pallete

3. Parachain(10001): Accountkey20(0X10101010111)

- An asset whose Id is 1 from pallet instance 50 in parachain 1001
  Relay: Parachain(1001)/PalletInstance(50)/GeneralIndex(1)
  Parchain1000: ../Parachain(1000)/PalletInstance(50)/GeneralIndex(1)
  Parachain1001: PalletInstance(50)/GeneralIndex(1)

- Pallet instance 10 in the relay chain
  Relay: Parachain(1001)/PalletInstance(10)
  Parachain1000: ../Parchain(1001)/PalletInstance(10)
  Parachain1001: Parchain(1000)/PalletInstance(10)

- An 80% backed governance origin in parachain 100
  Relay: Parachain(1001)/PalletInstance(10)
  Parachain1000: ../Parchain(1001)/PalletInstance(10)
  Parachain1001: Parchain(1000)/PalletInstance(10)

- The technical committee origin in the relay chain

Hint: Use https://github.com/paritytech/polkadot/blob/master/xcm/src/v3/junction.rs to inspect for existing Junctions
