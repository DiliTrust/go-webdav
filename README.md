# Go WebDAV

This is a fork of the [golang.org/x/net/webdav](https://pkg.go.dev/golang.org/x/net/webdav)
package, provided in the Golang SDK.

The reason for this fork is that the original package seems to be in maintenance mode,
with no new features or fixes.

## What this provides

Although the `golang.org/x/net/webdav` package covers most of our requirements,
we encountered issues when using MS Word to open documents concurrently.
Specifically, when MS Word opens a locked file, it initially opens in read-only mode.
After a few seconds, it incorrectly reports that the document is available for editing,
despite the lock still being in place, and without verifying that the file is lock-free.
Our goal is to resolve this behavior.