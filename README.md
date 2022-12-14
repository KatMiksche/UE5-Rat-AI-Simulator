# UE5-Rat-AI-Simulator
Little game with AI rats, modelling behaviour and reproduction
(uncooked UE 5.0.3 project)

How to use: For whole project download all 4 zip files and unpack. If you want to see just programming, uasset files are available separatelly

Rules of game:
- Food is spawning and disapearing automatically based on settings
- If rat food variable is on max, object is ignored
- Rat Food is depliting, if no food left, health is depliting
- Health is increasing if at least one food available
- Beta always evade Alpha, Female sometimes evade Alpha based on settings
- Alpha chase everyone
- Everyone ignore Beta and children
- When Alpha mate with Female, Female becomes pregnant and then gives birth to random number of offsprings of random roles - chance for role, min-max offsprings, length of pregnancy and protected time of children can be changed by variable
- Players health can be set separately in override variable, Role and State is given by default value of variables (recommended Alpha and Roaming), speed is given by Max Walk Speed

Variables influencing game:
- BP_Food: Initial Life Span (BP option)
- BP_AIratGame: RatsSpeed, FoodSpawnTimeRate
- BP_AIratController: PercentageFemaleEvade
- BP_Rat: HealthFood category of variables: Health, MaxHealth, Food, MaxFood, FoodDeplitionTimeRate, HealingTimeRate, PlayerHealthOverride
- BP_Rat: PregnancyVars category of variables: LengthOfPregnancy, MaxOffsprings, MinOffsprings, ChildProtectedTime, ChanceOfFemale, ChanceOfMale
- BP_Rat: LifeSpanInMinutes, LengthOfBlindnessAfterFight, ActorRole, ActorState, Max Walk Speed (BP option)

Programming notes:
- Gameplay tags are used directly on character
- Behaviour is run by behaviour tree based on gameplay tag casted to blackboard
- Change in behaviour is made by programmed listeners in AI controller which update blackboard and restart behaviour tree

Improvements to be considered :-) :
- SpeedUp rate in behaviour tree as variable set in gamemode
- Repair of chase to keep locked on target - either movement by blueprint or gameplay tags implemented to EQS
- Use of arrays and maps for multiple variables, for example hit rates in different interactions
- Use thirdperson template instead of topdown template
- Investigate errors caused by actors destroyed
