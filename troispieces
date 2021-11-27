local ServerHop = true 
local WebHook = "https://discord.com/api/webhooks/909478915788120154/oKUhNVdNE6I_fk_Fs0X_AtxbYM4nk5fkIWQXDivdiMT980OH5ZC71juKE-MZjsYqm4-C" --- WEBHOOK



if (not game:IsLoaded()) then
    game.Loaded:Wait();
end;

function webhooksend()
    if game:IsLoaded() then
    local req = syn.request
    local hwid_headers = {'Syn-Fingerprint'} -- You will have to add more headers for different exploits
    local data = {
    ["username"]  = "Doggo's fruit searcher(TRUE PIECE EDITION)",
    ["avatar_url"] = "https://cdn.discordapp.com/avatars/529978211988275211/11e3509be5ba316efa80fd65006d2ee1.webp?size=128",
    ["embeds"] = {
        {
            ["author"] = {
                ["name"] = game.Players.LocalPlayer.Name.. "Found a fruit !",
                ["url"] = "https://blox-fruits.fandom.com/wiki/Blox_Fruits",
                ["icon_url"] = "https://web.roblox.com/Thumbs/Avatar.ashx?x=100&y=100&Format=Png&userid="..game.Players.LocalPlayer.UserId
            },
            ["url"] = "https://www.roblox.com/games/"..game.PlaceId,
            ["description"] = game:GetService('MarketplaceService'):GetProductInfo(game.PlaceId).Name,
            ["color"] = 000000,
            ["fields"] = {
                {
                    ["name"] = "Ping",
                    ["value"] = "@everyone ",
                },
                {
                    ["name"] = "Player Info:",
                    ["value"] = "**Age: **"..game.Players.LocalPlayer.AccountAge,
                },
                {
                    ["name"] = "Fruit",
                    ["value"] = "**NAME: **"..v.Leaf.ProximityPromptDF.ObjectText,
                },
                {
                    ["name"] = "JobId:",
                    ["value"] = tostring("```"..game.JobId.."```"),
                    ["inline"] = true
                },
            },
            ["thumbnail"] = {
                ["url"] = "https://web.roblox.com/Thumbs/Avatar.ashx?x=100&y=100&Format=Png&userid="..game.Players.LocalPlayer.UserId
            },
            ["footer"] = {
                ["text"] = "Got a Fruit",
            }
        }
    }
}
local Post = req({Url = WebHook,  Method = 'POST', Headers = { ['Content-Type'] = 'application/json' }, Body = game:GetService('HttpService'):JSONEncode(data)})
end
end
    






function teleport()
    local Servers = game.HttpService:JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/"..game.PlaceId.."/servers/Public?sortOrder=Asc&limit=100"))
    for i,v in pairs(Servers.data) do
        if v.playing ~= v.maxPlayers then
            game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, v.id)
        end
    end
end


if ServerHop then
    while wait(30) do
        pcall(function()
            game:GetService("ReplicatedStorage").Remotes.StartUp:InvokeServer()
        end)
        wait(5)
        for i, v in pairs(game.Workspace.Map.Trees:GetChildren()) do
            if v:IsA("Model") and v:FindFirstChild("Leaf") and v:FindFirstChild("MeshPart1") then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Leaf.CFrame
                wait(.5)
                fireproximityprompt(v.Leaf.ProximityPromptDF)
                webhooksend()
                wait(0.1)
            end
        end
        wait(5)
        for i, v in pairs(game.Workspace:GetChildren()) do
            if v:IsA("Model") and v:FindFirstChild("Leaf") or v:IsA("Model") and v:FindFirstChild("Leaf") and v:FindFirstChild("MeshPart") then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Leaf.CFrame
                wait(.5)
                fireproximityprompt(v.Leaf.ProximityPromptDF)
                webhooksend()
                wait(0.1)
            end
        end
        syn.queue_on_teleport([[
            getgenv().ServerHop = true 
            loadstring(game:HttpGet("https://raw.githubusercontent.com/SenseiJoshy/Open-Source/main/Fruit%20Farm.lua"))()
        ]])
        repeat wait()
            teleport()
        until not ServerHop
    end
end
