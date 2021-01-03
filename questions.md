### Questions

#### Q1

There is many "Trait" names, do not you think that the "Trait" name should be rather "Config" or "Configuration", something like that?? Or I understand it wrong? My understaing is that the "Trait" is just "Config", I am right?

In `/recipes/pallets/check-membership/src/loose/mod.rs` there is example:

```rust
/// The pallet's configuration trait
/// Notice the loose coupling: any pallet that implements the `AccountSet` behavior works here.
pub trait Trait: system::Trait {
	/// The ubiquitous event type
	type Event: From<Event<Self>> + Into<<Self as system::Trait>::Event>;

	/// A type that will supply a set of members to check access control against
	type MembershipSource: AccountSet<AccountId = Self::AccountId>;
}
```

#### Q2

When I look at the code I got impression that everything in the code is `public`, I am probably wrong, what I do not know? I guess that there is some mechanism which makes the code private.

Example:

```rust
pub trait Trait: system::Trait {
	type Event: From<Event<Self>> + Into<<Self as system::Trait>::Event>;
}

decl_storage! {
	trait Store for Module<T: Trait> as Token {
		pub Balances get(fn get_balance): map hasher(blake2_128_concat) T::AccountId => u64;

		pub TotalSupply get(fn total_supply): u64 = 21000000;

		Init get(fn is_init): bool;
	}
}

decl_event!(
	pub enum Event<T>
	where
		AccountId = <T as system::Trait>::AccountId,
	{
		/// Token was initialized by user
		Initialized(AccountId),
		/// Tokens successfully transferred between users
		Transfer(AccountId, AccountId, u64), // (from, to, value)
	}
);
```

### Q3

There is any difference when I create new account via `dervied account` than let call it non-`dervied account`?

### Q4

Why there is NO SubSocial in fields for on-chain Identity? ;-)

---

## Questions on Monday's session

# Q1

What is the flow of the document: https://w3c.github.io/did-core/ I mean.. engines of web browser will implement the standard or it will works only on Pallet's site?

# Q2

There is any relation between `identity` and `did-pallet`?

# Q3

> This value MUST NOT contain "d", or any other members of the private information class as described in Registration Template. 

What is "d"? Just letter??? Why???

# Q4

https://github.com/paritytech/substrate-open-working-groups/discussions/2:

> Identity systems become unethical when they link users activities online in ways the user does not expect, which includes pressuring users to give unnecessarily information or unnecessarily link their activities.

Polkadot wants to connect all activity within the Internet/Polkadot ecosystem via Identity? 

Yay or Nein?

# Q5

https://github.com/substrate-developer-hub/substrate-enterprise-sample/compare/feat/did/trait#diff-bd184702627df6b90e236cf4b37b58d0514e1933a80995e2a5530dd2138f6dcfR18 ->

What is "Default"?

# Q6

> Instance1, what is that???

https://github.com/paritytech/substrate/pull/7599/files#diff-67684005af418e25ff88c2ae5b520f0c040371f1d817e03a3652e76b9485224aR610


# Q7

Where to start to study VRF? When/use case/situation do I need it, assuming I want to build parachain, I want to know Substrate framework?

# Q8

Any sentence on those three lines: https://github.com/paritytech/substrate/pull/7599/files#diff-426f1e122298e2af0cd2d47a85bfacad3a9728d3bedfcee34545a8b062774c3fR713-R716 ?
