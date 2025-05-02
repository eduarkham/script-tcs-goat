-- Auto Goat MPS - Script Base com Rayfield UI
-- Desenvolvido para testes no TCS/MPS - Versão inicial

-- Carregar a Rayfield Library
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Criar Janela principal
local Window = Rayfield:CreateWindow({
   Name = "Auto Goat MPS",
   LoadingTitle = "Auto Goat MPS",
   LoadingSubtitle = "By SeuNome",
   ConfigurationSaving = {
      Enabled = false
   },
   Discord = {
      Enabled = false
   },
   KeySystem = false
})

-- Aba Auto Skill
local AutoSkillTab = Window:CreateTab("Auto Skill", 4483362458)

-- Botão de Ativar Auto Skill
AutoSkillTab:CreateToggle({
   Name = "Ativar Auto Skill",
   CurrentValue = false,
   Flag = "AutoSkillToggle",
   Callback = function(Value)
      if Value then
         print("Auto Skill ativado")
         -- Exemplo: skill simples com F + X + N
         task.spawn(function()
            while Rayfield.Flags.AutoSkillToggle.Value do
               wait(1)
               keypress(Enum.KeyCode.F)
               wait(0.1)
               keypress(Enum.KeyCode.X)
               wait(0.1)
               keypress(Enum.KeyCode.N)
            end
         end)
      else
         print("Auto Skill desativado")
      end
   end,
})

-- Aba Auto Match
local AutoMatchTab = Window:CreateTab("Auto Match", 4483362458)

-- Botão de Ativar Auto Match
AutoMatchTab:CreateToggle({
   Name = "Ativar Auto Match",
   CurrentValue = false,
   Flag = "AutoMatchToggle",
   Callback = function(Value)
      if Value then
         print("Auto Match ativado")
         -- Coloque aqui sua lógica para movimentar jogador e detectar partida
         task.spawn(function()
            while Rayfield.Flags.AutoMatchToggle.Value do
               wait(1)
               -- Comportamento básico de treino (exemplo)
               print("Auto Match em execução...")
            end
         end)
      else
         print("Auto Match desativado")
      end
   end,
})
