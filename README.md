# release-grant-approval

A single static page that approves one release action, once.

An iOS release machine asks for a grant and prints a request. This page decodes
it, shows what it binds -- release, action, version, build, store digest -- and
asks a passkey to sign those exact bytes. The release machine verifies the
signature offline and records the grant.

- No server, no backend, no analytics, nothing stored anywhere.
- The private key is a passkey on the phone. It cannot be exported, and every
  use is gated by Face ID or a device PIN.
- Only the public half is published, in the fleet's own configuration.
- An approval covers the exact request it was shown, and nothing else.

The tooling that issues requests and verifies approvals is private.
