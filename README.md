# ERC2309
Experimental WARNING! ERC2309 prototype! Do not use in production!

I take NO RESPONSIBILITY whatsover for lost funds of any kind if you use this code, this is ONLY meant as a demonstration of the carbon emission reduction possibilities of ERC2309

# Notes on implementation

Batch minting happens in init function for now, but could be a call that can add more NFTs in a batch, with a new owner of those NFTs, so you could have

Alice mints 10k on init

Bob mints 5k

etc


And those would own the ranges,

alice: 0-9999

bob: 10000-14999


Ranges get broken up as NFTs are sold / transferred:

Charlie buys 500 from alice, now:


alice: 0-499, 501-9999,

charlie: 500-500,

bob: 10000-14999



As ranges are broken up to a certain degree, it becomes slow to lookup owner of a certain NFT by looping over the array, so you can set a saturation point for optimistic lookup.
Further improvement would be too lookup and search around that region if a hit isn't found on optimistic lookup.
