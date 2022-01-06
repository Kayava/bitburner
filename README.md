# Bitburner scripts collection

Welcome to the modified log of [Bitburner](https://danielyxie.github.io/bitburner/) scripts forked from [moriakaice](https://github.com/moriakaice/bitburner). They are written using the in-game language of NetscriptJS, which is a mutation of Javascript.

If you want to play the game itself - click on the name above.

This fork includes some fixes that were not in the original as of forking and some maybe some other changes that I played around with. Enjoy.

## Requirements

The script has been modified to be able to start on 8 GB (the default starting RAM for a player) on the `home` server. Obviously, when you expand the memory available, you'll get extra perks - being able to buy and manage player-owned servers, as well as using spare RAM to do actions.

The script can be slow to get going, but it'll get there eventually. Getting access to more port hackers will improve the performance.

## Installation

1. Create a new script called `start.ns` by issuing the following command: `nano start.ns`. Make sure you're on your home server if you're not (you can quickly go home by running `home` in the console).
2. Paste the following content:

```javascript
export async function main(ns) {
  if (ns.getHostname() !== "home") {
    throw new Exception("Run the script from home");
  }

  await ns.wget(
    `https://raw.githubusercontent.com/kayava/bitburner/master/src/initHacking.ns?ts=${new Date().getTime()}`,
    "initHacking.ns"
  );
  ns.spawn("initHacking.ns", 1);
}
```

3. Exit the nano and write in console: `run start.ns`
