## Canvas-chan

[![NPM](https://img.shields.io/badge/Available%20On-NPM-lightgrey.svg?logo=npm&logoColor=339933&labelColor=white&style=flat-square)](https://www.npmjs.com/package/@shineiichijo/canvas-chan)

Making canvas stuffs easier

---

### Installation
```
yarn add @shineiichijo/canvas-chan
```

## Features
- Simple to use
- Can be used for shipping people ❤️
- Can be used to make a person simp (ahm..)
- Generates image of Guess-The-Pokemon game (hidden and shown)
- And more...

# Usage

## Ship

```ts
import { Ship, IShipOptions } from '@shineiichijo/canvas-chan'
import { writeFile } from 'fs-extra'

(async () => {
    const options: IShipOptions = [
        {
            //name of the person1
            name: 'Person1',
            //image of the person1 (can be a Buffer)
            image: 'https://i.pinimg.com/originals/35/66/03/3566030107abb8193bfe646ee53ba3a0.jpg'
        },
        {
            //name of the person2
            name: 'Person2',
            //image of the person2 (can be a Buffer)
            image: 'https://i.pinimg.com/originals/5a/d2/0b/5ad20b2696a632543659055d62928028.jpg'
        }
    ]
    const level = Math.floor(Math.random() * 100)
    const ship = await new Ship(options, level, 'Amazing').build()
    //now let's write the image (Buffer)
    await writeFile('ship.png', ship)
})()
```

### Result 

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/ship.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/ship.png" alt="ship" border="0"></a>

</div>

## Simp

```ts
import { Simp } from '@shineiichijo/canvas-chan'
import { writeFile } from 'fs-extra'

(async () => {
    const simp = await new Simp('https://static.fandomspot.com/images/12/11202/05-makoto-itou-school-days-anime-screenshot.jpg').build() //the image can also be a Buffer
    //now let's write the image (Buffer)
    await writeFile('simp.png', simp)
})()
```

### Result

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/simp.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/simp.png" alt="simp" border="0"></a>

</div>

## Guess-The-Pokemon

```ts
import { Pokemon } from '@shineiichijo/canvas-chan'
import { writeFile } from 'fs-extra'
```

### Hidden

```ts
(async () => {
    const image = await new Pokemon(/**Name or Pokedex ID of the Pokemon*/'Chikorita', /**gonna hide it?*/ true).build()
    //now let's write the image (Buffer)
    await writeFile('hiddenPokemon.png', image)
})()
```

#### Result

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/hiddenPokemon.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/hiddenPokemon.png" alt="pokemon" border="0"></a>

</div>

### Shown

```ts
(async () => {
    const image = await new Pokemon(/**Name or Pokedex ID of the Pokemon*/'Chikorita', /**gonna hide it?*/ false).build()
    //now let's write the image (Buffer)
    await writeFile('shownPokemon.png', image)
})()
```

#### Result

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/shownPokemon.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/shownPokemon.png" alt="pokemon" border="0"></a>

</div>

## Triggered

```ts
import { Triggered } from '@shineiichijo/canvas-chan' //const { Triggered } = require('@shineiichijo/canvas-chan')
import { writeFile } from 'fs-extra'

(async () => {
    const triggered = await new Triggered('https://i.pinimg.com/originals/5a/d2/0b/5ad20b2696a632543659055d62928028.jpg').build()
    //now let's write the gif (Buffer)
    await writeFile('triggered.gif', triggered)
})()
```

### Result

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/triggered.gif"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/triggered.gif" alt="triggered" border="0"></a>

</div>

## Crush

```ts
import { Crush } from '@shineiichijo/canvas-chan' //const { Crush } = require(''@shineiichijo/canvas-chan')
import { writeFile } from 'fs-extra'

(async () => {
    const image = await new Crush('https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/bf447e2d-c744-4fb1-b4da-2630503601d2/d6kk0aq-b2032456-df83-4660-b4a4-7b7be582f5e9.png/v1/fill/w_1089,h_734,strp/tokisaki_kurumi_by_neostratos_d6kk0aq-pre.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MTM1MzciLCJwYXRoIjoiXC9mXC9iZjQ0N2UyZC1jNzQ0LTRmYjEtYjRkYS0yNjMwNTAzNjAxZDJcL2Q2a2swYXEtYjIwMzI0NTYtZGY4My00NjYwLWI0YTQtN2I3YmU1ODJmNWU5LnBuZyIsIndpZHRoIjoiPD0yMDA3MCJ9XV0sImF1ZCI6WyJ1cm46c2VydmljZTppbWFnZS5vcGVyYXRpb25zIl19.glklG5KmumFpSZbhBhu1Ow0b24ERYV3h99HMk4H_eXI')
    await writeFile('crush.png', image)
})()
```

## Result 

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/crush.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/crush.png" alt="crush" border="0"></a>

</div>

## Friendship

```ts
import { Friendship, IFriendShip } from '@shineiichijo/canvas-chan' //const { Friendship } = require('@shineiichijo/canvas-chan')
import { writeFile } from 'fs-extra'

(async () => {
    const options: IFriendShip = [
        {
            //name of the person1
            name: 'Person1',
            //image of the person1 (can be a Buffer)
            image: 'https://i.pinimg.com/originals/5a/d2/0b/5ad20b2696a632543659055d62928028.jpg'
        },
        {
            //name of the person2
            name: 'Person2',
            //image of the person2 (can be a Buffer)
            image: 'https://i.pinimg.com/originals/ea/b2/a4/eab2a46c041c81c781fff1ef0e355811.jpg'
        }
    ]
    const level = Math.floor(Math.random() * 100)
    const image = await new Frienship(options, level, 'Best Friends')
    //now let's write the image (Buffer)
    await writeFile('frienship.png', image)
})()
```

### Result

<div align=center>
<a href="https://github.com/ShineiIchijo/Canvas-chan/blob/master/.github/assets/friendship.png"><img src="https://raw.githubusercontent.com/ShineiIchijo/Canvas-chan/master/.github/assets/friendship.png" alt="friendship" border="0"></a>

</div>