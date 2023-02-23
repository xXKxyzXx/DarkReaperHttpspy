
local HttpService = game:GetService("HttpService")
local UserInputService = game:GetService("UserInputService")

local function MakeDraggable(topbarobject, object, state) 
	pcall(
		function()
			local dragging = false
			local dragInput, mousePos, framePos

			topbarobject.InputBegan:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 then
					dragging = true
					mousePos = input.Position
					framePos = object.Position

					input.Changed:Connect(function()
						if input.UserInputState == Enum.UserInputState.End then
							dragging = false
						end
					end)
				end
			end)

			topbarobject.InputChanged:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseMovement then
					dragInput = input
				end
			end)

			UserInputService.InputChanged:Connect(function(input)
				if input == dragInput and dragging and state then
					local delta = input.Position - mousePos
					object.Position  = UDim2.new(framePos.X.Scale, framePos.X.Offset + delta.X, framePos.Y.Scale, framePos.Y.Offset + delta.Y)
				end
			end)
		end
	)
end

local AutoSave = true
local LogsFolderName = "HttpSpy"
local FileData = nil
if not isfolder(LogsFolderName) then
	makefolder(LogsFolderName)
end

local DarkReaperHttpSpyUI = {}
local Framework = {}

Framework.wirteFile = function(FileName:string,Data:string)
	if isfolder(LogsFolderName) then
		writefile(LogsFolderName.."/"..FileName..".lua",tostring(Data))
		return true
	else
		return false
	end	
end

Framework.CopyScript = function(Url:string)
	if type(Url) == "string" then
		setclipboard(''..Url..'')
	end
end

DarkReaperHttpSpyUI.CreateUI = function()

	if game:WaitForChild("CoreGui"):FindFirstChild("DarkreaperHttpSpyV1") then
		game:WaitForChild("CoreGui"):FindFirstChild("DarkreaperHttpSpyV1"):Destroy()
	end

	local Buttons = {}

	local DarkreaperHttpSpyV1 = Instance.new("ScreenGui")
	local Background = Instance.new("Frame")
	local UP = Instance.new("Frame")
	local DarkReaper = Instance.new("TextLabel")
	local Down = Instance.new("Frame")
	local Settings = Instance.new("ImageButton")
	local TextLabel = Instance.new("TextLabel")
	local LogHolder = Instance.new("ScrollingFrame")
	local UIListLayout = Instance.new("UIListLayout")

	local Backgroundforokay = Instance.new("Frame")
	local NameFile = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local FileBox = Instance.new("TextBox")
	local UICorner_2 = Instance.new("UICorner")
	local Okay = Instance.new("TextButton")
	local UICorner_3 = Instance.new("UICorner")
	local SettingsFrame = Instance.new("Frame")
	local AutoSave = Instance.new("Frame")
	local UICorner_4 = Instance.new("UICorner")
	local TextLabel_2 = Instance.new("TextLabel")
	local Toggle = Instance.new("TextButton")
	local UICorner_5 = Instance.new("UICorner")

	DarkreaperHttpSpyV1.Name = "DarkreaperHttpSpyV1"
	DarkreaperHttpSpyV1.Parent = game:WaitForChild("CoreGui")

	Background.Name = "Background"
	Background.Parent = DarkreaperHttpSpyV1
	Background.BackgroundColor3 = Color3.fromRGB(43, 43, 43)
	Background.BorderSizePixel = 0
	Background.Position = UDim2.new(0.5, -251, 0.5, -125)
	Background.Size = UDim2.new(0, 502, 0, 250)

	UP.Name = "UP"
	UP.Parent = Background
	UP.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
	UP.BorderColor3 = Color3.fromRGB(255, 255, 255)
	UP.BorderSizePixel = 0
	UP.Size = UDim2.new(0, 500, 0, 37)

	DarkReaper.Name = "DarkReaper"
	DarkReaper.Parent = UP
	DarkReaper.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	DarkReaper.BackgroundTransparency = 1.000
	DarkReaper.Position = UDim2.new(0, 0, 0.351351351, 0)
	DarkReaper.Size = UDim2.new(0, 185, 0, 10)
	DarkReaper.Font = Enum.Font.SourceSans
	DarkReaper.Text = "Darkreaper HttpSpy V1"
	DarkReaper.TextColor3 = Color3.fromRGB(255, 255, 255)
	DarkReaper.TextSize = 18.000

	Down.Name = "Down"
	Down.Parent = Background
	Down.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
	Down.BorderColor3 = Color3.fromRGB(255, 255, 255)
	Down.BorderSizePixel = 0
	Down.Position = UDim2.new(0, 0, 0.839999974, 0)
	Down.Size = UDim2.new(0, 500, 0, 40)

	Settings.Name = "Settings"
	Settings.Parent = Down
	Settings.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Settings.BackgroundTransparency = 1.000
	Settings.Position = UDim2.new(0.920000017, 0, 0, 0)
	Settings.Size = UDim2.new(0, 40, 0, 40)
	Settings.Image = "http://www.roblox.com/asset/?id=6031280882"

	TextLabel.Parent = Down
	TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel.BackgroundTransparency = 1.000
	TextLabel.Position = UDim2.new(0.0300000012, 0, 0.25, 0)
	TextLabel.Size = UDim2.new(0, 82, 0, 20)
	TextLabel.Font = Enum.Font.SourceSans
	TextLabel.Text = "Kxyz#7507"
	TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel.TextSize = 20.000

	LogHolder.Name = "LogHolder"
	LogHolder.Parent = Background
	LogHolder.Active = true
	LogHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	LogHolder.BackgroundTransparency = 1.000
	LogHolder.Position = UDim2.new(0, 0, 0.148000002, 0)
	LogHolder.Size = UDim2.new(0, 500, 0, 173)
	LogHolder.ScrollBarThickness = 2

	UIListLayout.Parent = LogHolder
	UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder

	Backgroundforokay.Name = "Backgroundforokay"
	Backgroundforokay.Parent = Background
	Backgroundforokay.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
	Backgroundforokay.BackgroundTransparency = 0.350
	Backgroundforokay.BorderSizePixel = 0
	Backgroundforokay.Position = UDim2.new(0, 0, 0.148000002, 0)
	Backgroundforokay.Size = UDim2.new(0, 499, 0, 173)
	Backgroundforokay.Visible = false

	NameFile.Name = "NameFile"
	NameFile.Parent = Backgroundforokay
	NameFile.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
	NameFile.Position = UDim2.new(0.330661297, 0, 0.294797689, 0)
	NameFile.Size = UDim2.new(0, 154, 0, 71)

	UICorner.Parent = NameFile

	FileBox.Name = "FileBox"
	FileBox.Parent = NameFile
	FileBox.BackgroundColor3 = Color3.fromRGB(79, 79, 79)
	FileBox.Position = UDim2.new(0.116883114, 0, 0.267605633, 0)
	FileBox.Size = UDim2.new(0, 126, 0, 18)
	FileBox.Font = Enum.Font.SourceSans
	FileBox.PlaceholderText = "Enter File Name..."
	FileBox.Text = ""
	FileBox.TextColor3 = Color3.fromRGB(0, 0, 0)
	FileBox.TextSize = 18.000

	UICorner_2.Parent = FileBox

	Okay.Name = "Okay"
	Okay.Parent = NameFile
	Okay.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
	Okay.Position = UDim2.new(0.214285716, 0, 0.676056325, 0)
	Okay.Size = UDim2.new(0, 88, 0, 16)
	Okay.Font = Enum.Font.SourceSans
	Okay.Text = "Okay!"
	Okay.TextColor3 = Color3.fromRGB(255, 255, 255)
	Okay.TextSize = 14.000

	Okay.MouseButton1Click:Connect(function()
		Framework.wirteFile(FileBox.Text,FileData)
		Backgroundforokay.Visible = false
	end)
	UICorner_3.Parent = Okay

	SettingsFrame.Name = "SettingsFrame"
	SettingsFrame.Parent = Background
	SettingsFrame.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
	SettingsFrame.BorderSizePixel = 0
	SettingsFrame.Position = UDim2.new(0, 0, 0.148000002, 0)
	SettingsFrame.Size = UDim2.new(0, 500, 0, 173)
	SettingsFrame.Visible = false

	AutoSave.Name = "AutoSave"
	AutoSave.Parent = SettingsFrame
	AutoSave.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
	AutoSave.Position = UDim2.new(0.0500000007, 0, 0.138728321, 0)
	AutoSave.Size = UDim2.new(0, 124, 0, 35)

	UICorner_4.Parent = AutoSave

	TextLabel_2.Parent = AutoSave
	TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.BackgroundTransparency = 1.000
	TextLabel_2.Position = UDim2.new(0.0403225794, 0, 0.171428576, 0)
	TextLabel_2.Size = UDim2.new(0, 71, 0, 20)
	TextLabel_2.Font = Enum.Font.SourceSans
	TextLabel_2.Text = "AutoSave"
	TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.TextSize = 18.000

	Toggle.Name = "Toggle"
	Toggle.Parent = AutoSave
	Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Toggle.Position = UDim2.new(0.725806415, 0, 0.114285715, 0)
	Toggle.Size = UDim2.new(0, 25, 0, 25)
	Toggle.Font = Enum.Font.SourceSans
	Toggle.Text = ""
	Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
	Toggle.TextSize = 14.000

	UICorner_5.Parent = Toggle

	MakeDraggable(UP,Background, true)

	Toggle.MouseButton1Click:Connect(function()
		if Toggle.BackgroundColor3 == Color3.fromRGB(255,255,255) then
			AutoSave = false
			Toggle.BackgroundColor3 = Color3.fromRGB(49,49,49)
		else
			AutoSave = true
			Toggle.BackgroundColor3 = Color3.fromRGB(255,255,255)
		end
	end)

	Settings.MouseButton1Click:Connect(function()

		if Backgroundforokay.Visible == true then
			Backgroundforokay.Visible = false
		end
		if SettingsFrame.Visible == false then
			SettingsFrame.Visible = true
		else
			SettingsFrame.Visible = false
		end
	end)

	Buttons.CreateButtons = function(MethodData,UrlData)

		local Functions = {}

		local Log = Instance.new("Frame")
		local Url = Instance.new("TextLabel")
		local Method = Instance.new("TextLabel")
		local Border = Instance.new("Frame")
		local CopyScript = Instance.new("ImageButton")
		local SaveAsFile = Instance.new("ImageButton")

		Log.Name = "Log"
		Log.Parent = LogHolder
		Log.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
		Log.BorderSizePixel = 0
		Log.Position = UDim2.new(0.0539999977, 0, 0, 0)
		Log.Size = UDim2.new(0, 493, 0, 52)

		Url.Name = "Url"
		Url.Parent = Log
		Url.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Url.BackgroundTransparency = 1.000
		Url.Position = UDim2.new(0.0324543007, 0, 0.474183351, 0)
		Url.Size = UDim2.new(0, 360, 0, 15)
		Url.Font = Enum.Font.SourceSans
		Url.Text = "Url : "..UrlData .. "\n"
		Url.TextColor3 = Color3.fromRGB(255, 255, 255)
		Url.TextSize = 10.000
		Url.TextStrokeTransparency = 0.000
		Url.TextWrapped = true

		Method.Name = "Method"
		Method.Parent = Log
		Method.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Method.BackgroundTransparency = 1.000
		Method.Position = UDim2.new(0.0324543007, 0, 0.19178082, 0)
		Method.Size = UDim2.new(0, 100, 0, 15)
		Method.Font = Enum.Font.SourceSans
		Method.Text = "Method : " ..MethodData .."\n"
		Method.TextColor3 = Color3.fromRGB(255, 255, 255)
		Method.TextSize = 10.000
		Method.TextStrokeTransparency = 0.000
		Method.TextWrapped = true

		Border.Name = "Border"
		Border.Parent = Log
		Border.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Border.BorderColor3 = Color3.fromRGB(255, 255, 255)
		Border.Size = UDim2.new(0, 1, 0, 52)

		CopyScript.Name = "CopyScript"
		CopyScript.Parent = Log
		CopyScript.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		CopyScript.BackgroundTransparency = 1.000
		CopyScript.Position = UDim2.new(0.874239385, 0, 0.269230783, 0)
		CopyScript.Size = UDim2.new(0, 20, 0, 20)
		CopyScript.Image = "http://www.roblox.com/asset/?id=6035053278"

		SaveAsFile.Name = "SaveAsFile"
		SaveAsFile.Parent = Log
		SaveAsFile.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		SaveAsFile.BackgroundTransparency = 1.000
		SaveAsFile.Position = UDim2.new(0.933062911, 0, 0.269230753, 0)
		SaveAsFile.Size = UDim2.new(0, 20, 0, 20)
		SaveAsFile.Image = "http://www.roblox.com/asset/?id=6035067842"

		SaveAsFile.MouseButton1Click:Connect(function()
			if Backgroundforokay.Visible == false then
				Backgroundforokay.Visible = true
				FileData = 'Method : '..MethodData .."\n" .. 'Url : ' ..UrlData
			end
		end)

		CopyScript.MouseButton1Click:Connect(function()
			if type(UrlData) == "table" then
				Framework.CopyScript(MethodData.."('"..UrlData.."')")
			else
				Framework.CopyScript(UrlData)
			end
		end)

		LogHolder.CanvasSize = UDim2.new(0, 0, 0, UIListLayout.AbsoluteContentSize.Y)

		return Functions
	end
	return Buttons
end

local format = "console"
local Logs = {}

local Print = function(...)

	if format == "console" then

	elseif format == "Robloxconsole" then
		print(...)
	elseif format == "UI" then

	end

end
local oldHttpGet 

local UI = DarkReaperHttpSpyUI.CreateUI()

oldHttpGet = hookfunction(game.HttpGet,function(self,...)
	print(tostring(self.Name..":HttpGet"),...)
	UI.CreateButtons("game.HttpGet",...)
	if AutoSave then
		Framework.wirteFile(tostring(os.clock().."AutoSave"), "Method : game.HttpGet" .. "\n"  .. "Url : "  .. ...)
		return oldHttpGet(self,...)
	end
	return oldHttpGet(self,...)
end)


local OldHttpGetAsync

OldHttpGetAsync = hookfunction(game.HttpGetAsync,function(self,...)
	print(tostring(self.Name..":HttpGetAsync"),...)
	UI.CreateButtons("game.HttpGetAsync",...)

	if AutoSave then
		return OldHttpGetAsync(self,...)
	end
	return OldHttpGetAsync(self,...) 
end)

local OldGetObjects
OldGetObjects = hookfunction(game.GetObjects,function(self,...)
	print(tostring(self.Name..":GetObjects"),...)
	UI.CreateButtons("game.GetObjects",...)
	if AutoSave then
		return OldGetObjects(self,...)
	end
	return OldGetObjects(self,...) 
end)
local OldHttpPost

OldHttpPost = hookfunction(game.HttpPost,function(self,...)
	print(tostring(self.Name..":HttpPost"),...)
	UI.CreateButtons("game.HttpPost",...)
	if AutoSave then
		return OldHttpPost(self,...)
	end
	return OldHttpPost(self,...) 
end)

local OldHttpPostAsync

OldHttpPostAsync = hookfunction(game.HttpPostAsync,function(self,...)
	print(tostring(self.Name..":HttpPostAsync"),...)
	UI.CreateButtons("game.HttpPostAsync",...)
	if AutoSave then
		return OldHttpPostAsync(self,...)
	end
	return OldHttpPostAsync(self,...) 
end)

local OldRequest

OldRequest = hookfunction(request,function(self,...)
	if not self then return end
	UI.CreateButtons("request",tostring(self.Url))
	if AutoSave then
		return OldRequest(self,...)
	end
	return OldRequest(self,...) 
end)

--More Fixes soon
