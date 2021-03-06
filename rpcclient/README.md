rpcclient
=========

[![Build Status](http://img.shields.io/travis/brsuite/brond.svg)](https://travis-ci.org/brsuite/brond)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/brsuite/brond/rpcclient)

rpcclient implements a Websocket-enabled Brocoin JSON-RPC client package written
in [Go](http://golang.org/).  It provides a robust and easy to use client for
interfacing with a Brocoin RPC server that uses a brond/brocoin core compatible
Brocoin JSON-RPC API.

## Status

This package is currently under active development.  It is already stable and
the infrastructure is complete.  However, there are still several RPCs left to
implement and the API is not stable yet.

## Documentation

* [API Reference](http://godoc.org/github.com/brsuite/brond/rpcclient)
* [brond Websockets Example](https://github.com/brsuite/brond/tree/master/rpcclient/examples/bronwebsockets)
  Connects to a brond RPC server using TLS-secured websockets, registers for
  block connected and block disconnected notifications, and gets the current
  block count
* [bronwallet Websockets Example](https://github.com/brsuite/brond/tree/master/rpcclient/examples/bronwalletwebsockets)
  Connects to a bronwallet RPC server using TLS-secured websockets, registers for
  notifications about changes to account balances, and gets a list of unspent
  transaction outputs (utxos) the wallet can sign
* [Brocoin Core HTTP POST Example](https://github.com/brsuite/brond/tree/master/rpcclient/examples/brocoincorehttp)
  Connects to a brocoin core RPC server using HTTP POST mode with TLS disabled
  and gets the current block count

## Major Features

* Supports Websockets (brond/bronwallet) and HTTP POST mode (brocoin core)
* Provides callback and registration functions for brond/bronwallet notifications
* Supports brond extensions
* Translates to and from higher-level and easier to use Go types
* Offers a synchronous (blocking) and asynchronous API
* When running in Websockets mode (the default):
  * Automatic reconnect handling (can be disabled)
  * Outstanding commands are automatically reissued
  * Registered notifications are automatically reregistered
  * Back-off support on reconnect attempts

## Installation

```bash
$ go get -u github.com/brsuite/brond/rpcclient
```

## License

Package rpcclient is licensed under the [copyfree](http://copyfree.org) ISC
License.
