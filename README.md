repeat wait()
until game:IsLoaded()

wait(1)

function Get_Board()
    for i,v in pairs(workspace.Boards:GetChildren()) do
        if v.Player1.Value == nil and v.Player2.Value == nil then
            return v
        end
    end
end

function Dupe(board)
end

function Drop(amt)
    for i=1, amt do
        game:GetService("ReplicatedStorage").RemoteEvents.Equip:FireServer(getgenv().item_name)
        wait(0.7)
        game:GetService("ReplicatedStorage").RemoteEvents.Drop:FireServer(getgenv().item_name)
        wait(0.7)
    end
end

local board = Get_Board()

local platform = Instance.new("Part")
platform.Parent = workspace
platform.Position = Vector3.new(board.MAIN.CFrame.X, board.MAIN.CFrame.Y + 10, board.MAIN.CFrame.Z + 10)
platform.Anchored = true

wait()

Drop(15)
wait(1)
Dupe(board)
