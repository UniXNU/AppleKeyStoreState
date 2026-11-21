# AppleKeyStoreState

AppleKeyStore state and selector handling.

used with `aks=1`.

Key wrapping is software: the device key derives from the identity the board returns through `native_aks_device_id`, and the board must return one. This is not hardware data protection. Reference key operations and device lock stay unsupported.

For device state queries (`17`, `35`), device and system handles (`0`, `-3`) return the configured device lock state, while per-user macOS session handles (`< -3`, e.g. `-501`) return `kIOReturnNotFound` because no per-user SEP keybag exists.

Build and interface details: [documentation](https://unixnu.com/reference/components). Component sources and dependencies: [catalog](https://unixnu.com/reference/components).
