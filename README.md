RbxNet Id
==============
Id generator for RbxNet.


## What it is for

Obfuscating the IDs of RemoteEvents/RemoteFunctions. 
Since a `const enum` in roblox-ts is compiled as the value of the enum (e.g. `RemoteId.A` will turn into `"<random guid A>"`)


## Usage


```
rbxnid
```
It will use the root directory this way, and will find all .id.json files that match and generate respective .d.ts with enums in them.

Example `remoteId.id.json` file
```json
{
	"Name": "RemoteId",
	"IDs": [
		"A",
		"B",
		"C"
	]
}
```

will generate (`remoteId.d.ts`):


```ts
export const enum RemoteId {
    A = "<random guid A>",
	B = "<random guid B>",
	C = "<random guid C>"
}
```
