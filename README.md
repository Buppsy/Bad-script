--# SHITTY SCRIPT MOMENT
-- here u go
-- sub to hype! (no sponsor lol)
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Bush", "GrapeTheme")



      --MAIN shit
local Main = Window:NewTab("Hacki shit test")
local MainSection = Tab:NewSection("Stuff")
Section:UpdateSection("Stuff")
Section:NewLabel("LabelText")
Section:NewButton("Silent aim load", "made by Ave.", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Averiias/Universal-SilentAim/main/main.lua"))()
end)
Section:NewButton("TC2 Birb Breaker.", "made by Trashjpg", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Trashjpg/Rage/main/TC2.lua"))()
end)
Section:NewButton("Infinite yield.", "Good for click tp i guess.", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))() 
end)
Section:NewButton("homemade esp (shit)", " = for toggle", function()
    local setkey = "=" -- change to something like "g" or whatever to change it
local waitduration = 0 -- the amount of time before the ESP updates (removes all current ESP objects and makes new ones)

--=You can edit below if u want (buppsy = bush + huppsy)=--


local plr = game:GetService('Players').LocalPlayer

function getteam(plr) -- yeah i did this instead of getting their actual team because for some reason that doesnt work sometimes idk why
	local thang = nil
	if plr.TeamColor then
		for i,v in pairs(game:GetService('Teams'):GetChildren()) do
			if v.TeamColor == plr.TeamColor then
				thang = v
			end
		end
	end
	return thang
end

local plr = game:GetService('Players').LocalPlayer
if plr:FindFirstChild('Zz1pF800p8lDrsOQgGiqa') ==nil then
	

local thingy = Instance.new('IntValue',plr)
thingy.Name="Zz1pF800p8lDrsOQgGiqa"
thingy.AncestryChanged:connect(function()
	wait()
	thingy.Parent = plr
end)
local mou = plr:GetMouse()
local active = false

function invert(Color)
	return Color3.new((255 - Color.r * 255)/255, (255 - Color.g * 255)/255, (255 - Color.b * 255)/255)
end

function heil()
	for i,v in pairs(game:GetService('CoreGui'):GetChildren()) do
		if v:IsA('Folder') and (game:GetService('Players'):FindFirstChild(v.Name) or v:FindFirstChildOfClass("BillboardGui") or v:FindFirstChildOfClass("BoxHandleAdornment")) then
			v:Destroy()
		end
	end
	if active == true then
		for i,v in pairs(game:GetService('Players'):GetChildren()) do
			if v.Character and v~=plr then
				if game:GetService('CoreGui'):FindFirstChild(v.Name) == nil then
					local folder = Instance.new('Folder',game:GetService('CoreGui'))
					folder.Name = v.Name
					if v.Character:FindFirstChild('Head') then
						local gui = Instance.new('BillboardGui',folder)
						gui.Adornee = v.Character.Head
						gui.AlwaysOnTop = true
						gui.LightInfluence = 0
						gui.Size = UDim2.new(10,0,2,0)
						gui.StudsOffset=Vector3.new(0,4,0)
						local text = Instance.new('TextLabel',gui)
						if getteam(v) then
							text.BackgroundColor3 = v.TeamColor.Color
							text.TextColor3 = invert(v.TeamColor.Color)
							text.BorderColor3 = v.TeamColor.Color
						else
							text.BackgroundColor3 = Color3.new(1,1,1)
							text.TextColor3 = Color3.new(0,0,0)
							text.BorderColor3 = Color3.new(1,1,01)
						end
						text.BorderSizePixel = 2
						text.Size = UDim2.new(1,0,1,0)
						text.TextScaled = true
						text.Text = v.Name
						text.TextYAlignment = Enum.TextYAlignment.Top
						text.Font = Enum.Font.SourceSansBold
						local text2 = Instance.new('TextLabel',text)
						text2.BackgroundTransparency = 1
						text2.Size = UDim2.new(1,0,0.3,0)
						text2.Position = UDim2.new(0,0,0.7,0)
						text2.TextScaled = true
						if getteam(v) then
							text2.Text = [[Team: "]]..getteam(v).Name..[["]]
						else
							text2.Text = [[Team: "None"]]
						end
						text2.Font = Enum.Font.SourceSansBold
						if getteam(v) then
							text2.TextColor3 = invert(v.TeamColor.Color)
						else
							text2.TextColor3 = Color3.new(0,0,0)
						end
					end
					if (v.Character:FindFirstChild('Head')) then
					for _,part in pairs(v.Character:GetChildren()) do
						if part:IsA('BasePart') then
							local coru=coroutine.wrap(function()
							local endtransparency = part.Transparency
							local adorn = Instance.new('BoxHandleAdornment',folder)
							adorn.Name = v.Name
							if part.Name ~= "Head" then
								adorn.Size = part.Size
							else
								adorn.Size = (part.Size)-Vector3.new(part.Size.X/2,0,0)
							end
							adorn.Adornee = part
							adorn.AlwaysOnTop = true
							adorn.ZIndex = 5
							adorn.Transparency = endtransparency
							adorn.Color3 = Color3.fromRGB(255, 44, 17)
							local adorn2 = Instance.new('BoxHandleAdornment',folder)
							adorn2.Name = v.Name
							if part.Name ~= "Head" then
								adorn2.Size = part.Size*1.1
							else
								adorn2.Size = (part.Size*1.1)-Vector3.new(part.Size.X/2,0,0)
							end
							adorn2.Adornee = part
							adorn2.AlwaysOnTop = true
							adorn2.ZIndex = 2
							adorn2.Transparency = endtransparency+0.1
							adorn2.Color3 = Color3.fromRGB(183, 209, 73)
							local adorn3 = Instance.new('BoxHandleAdornment',folder)
							adorn3.Name = v.Name
							if part.Name ~= "Head" then
								adorn3.Size = part.Size*1.15
							else
								adorn3.Size = (part.Size*1.15)-Vector3.new(part.Size.X/2,0,0)
							end
							adorn3.Adornee = part
							adorn3.AlwaysOnTop = true
							adorn3.ZIndex = 1
							adorn3.Transparency = endtransparency+0.2
							adorn3.Color3 = Color3.fromRGB(35, 166, 184)
							end)
							coru()
						end
					end
					end
				end
			end
		end
	end
end

mou.KeyDown:connect(function(key)
	if key==setkey then
		active = not active
	end
end)

while true do
	heil()
	wait(waitduration)
end

end
end)
Section:NewToggle("ToggleText", "ToggleInfo", function(state)
    if state then
        game.LocalPlayer.Character.Humanoid.Walkspeed = 50
		game.LocalPlayer.Character.Humanoid.JumpPower = 120
    else
       game.LocalPlayer.Character.Humanoid.Walkspeed = 16
	   game.LocalPlayer.Character.Humanoid.JumpPower = 50
    end
end)

--LOCAL PLAYER

local Player = Window:NewTab("Character")
local PlayerSection = Tab:NewSection("Epic WS slider")
PlayerSection:NewSlider("Walkspeed", "u k what it fucking means", 500, 5, function(s) -- 500 (MaxValue) | 5 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

local PlayerSection = Tab:NewSection("epic jp slider")
PlayerSection:NewSlider("JumpPower", "make u jump high", 500, 5 function (s) -- 350 (maxvalue) | 5 (minvalue)
	game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)



 --Other shit (trolley stuff)
 local BALLS = Window:NewTab("Other shit")
 local BALLSSection = Tab:NewSection("Other shit")
 Section:NewButton("Chat spoofer", "Does what that it says bro", function()
	loadstring(game:HttpsGet(("https://pastebin.com/raw/djBfk8Li"),true))()
end)
