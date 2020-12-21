### Questions

#### Q1

There is many "Trait" names, do not you think that the "Trait" name should be rather "Config" or something like that?? Or I understand it wrong? My understaing is that the "Trait" is just "Config", I am right?

In `/recipes/pallets/check-membership/src/loose/mod.rs` there is:

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
