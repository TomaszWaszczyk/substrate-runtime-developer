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
