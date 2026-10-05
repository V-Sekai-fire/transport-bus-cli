# transport-bus-cli

A command-line transport that sends one command over the harness command bus and prints the interactor's reply.

## What it is for

It reaches an interactor through the same request envelope and services as any other transport, so a command that works here works there, and one that fails is the interactor's fault. An interactor's error is still a reply and exits non-zero, so the tool serves as a check as well as a viewer. Its reply reader decodes only the CBOR kinds a reply is made of and refuses anything else.

## Build and run

The first command sends one command to whichever interactor is on the bus and needs the harness's Python package, `third_party/harness/python`, on the path. The second checks the reply reader against bytes the interactors write and runs without it.

```sh
python -m buscli <command>
python proof/test_cbor.py
```

## Licence

LICENSE is MIT, while the Python sources carry Apache-2.0 SPDX headers.
