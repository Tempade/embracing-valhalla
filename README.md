################################################
#   Embracing Valhalla (Custom Game Project)
#   Tyler Nichols
#   Created 11/18/20
################################################

Controls:
	1.) WASD / Arrow Keys			2.) Spacebar
		- Move Left and Right			- Jump / Continue Monologue
	3.) Left Click					4.) Right Click
		- Light Attack						- Heavy Attack, Block, Throw Weapon
	5.) ESC Key						6.) E Key
		- Skip Monologue				- Pick up Weapon / Switch between Overworld and Underworld
	7.) Shift Key
		- Sprint



Implemented Mechanics (Created by me unless specified otherwise):

						------------------------- MAIN MENU -------------------------
		1.) Cloud Spawning
			- Locations of screen: Upper 33% of screen, Middle 33% of screen, Lower 33% of screen
			- Will never instantiate same sprite or same location twice in a row
			- Destroys clouds after leaving screen
		2.) Play Button
			- Loads "Stage_One" scene
		3.) Controls Button
			- Loads "Controls" scene to inform player of controls for the game
		4.) Exit Button
			- Exits the game
		5.) Transition
			- After clicking "Play" Button, screen fades in then out of white to hide scene change

						------------------------- PLAYER -------------------------
		1.) Movement
			- Player can move left/right, and jump
			- Player movespeed is slowed while attacking
			- Player movespeed is doubled while sprinting
		2.) Attack
			- Player can attack, block, or throw weapon depending on wielded weapon
			- Player will attack in direction they are currently facing
		3.) Interactions
			- Player can pick up weapons
			- Player can swap between Overworld and Underworld

						------------------------- WEAPONS -------------------------
		1.) Abilities
			- None: Player cannot attack without a weapon
			- Axe: Player can light attack or heavy attack
			- Spear: Player can light attack or throw weapon
			- Sword: Player can light attack or block
		2.) Stats
			- Axe: Short range, moderate damage, slow/fast speed
			- Spear: Long range, low damage, fast speed
			- Sword: Moderate range, high damage, slow speed
		3.) Types of Attacks
			- Light Attack:
				* Normal attack for Spear and Sword
				* Fast speed, low damage, doesn't knockback for Axe
			- Heavy Attack: Slow speed, high damage, knockback
			- Throw: Throws current weapon, sets wielded weapon to none, and is able to be picked up again
			- Block: Negates any damage that would be taken while blocking, can only be held for 2 seconds

						------------------------- ENEMIES -------------------------
		1.) Stats
			- All enemies have Health, Attack Damage, Movement Speed, knockback strength, and Option to enable Knockback
		2.) Cartoon Viking
			- Idle in Pose01 until Player enters detection trigger
			- After triggered, switches to Pose02 and begins to move towards Player after a short delay
			- Will also switch poses if hit with a ranged attack from outside detection zone
			- When Player is in attack range, attempts to attack Player
		
						------------------------- CAMERAS -------------------------
		1.) Cutscenes
			- I created a method to disable the main camera and enable a temporary camera for cutscenes
			- A second method will disable the temporary camera and enable the main camera again
		2.) Camera Follow
			- The main camera will interpolate to different locations when triggered by Player movement
		3.) Monologue
			- At many points in the game, the user will interact with their character's monologue
		4.) Decision Making
			- At some points, the user will need to make decisions by clicking 1 of 3 buttons

						------------------------- ANIMATIONS -------------------------
		* Notes
			- Number in brackets is total # of animations for each bulletpoint ([4] = 4 animations)
			- No number in brackets means only 1 animation
			- All character animations have an animation for facing left AND for facing right (Reason for so many animations)
			- Asterisk next to animation means it was created by me, otherwise it was not ([*])
		1.) Player
			- [8] Idle no weapon / Idle with weapon (Axe,Spear,Sword)				- [8] Moving no weapon / Moving with weapon (Axe,Spear,Sword)
			- [8] Knockback no weapon / Knockback with weapon (Axe,Spear,Sword)		- [6] Light Attack with weapon (Axe,Spear,Sword)
			- [6] Pickup weapon (Axe,Spear,Sword)									- [2] Heavy Attack with Axe
			- Block																	- Death
		2.) CartoonViking
			- [4] Idle Pose01 / Pose02												- [4] Knockback Pose01 / Pose02
			- [2] Transition Pose01 to Pose02										- [2] Attack
			- [4] Death Pose01 / Pose02												- [4] Run Pose01 / Pose02
		3.) Environment
			- Dark Torch															- Drakkar (Vking Ship)
			- Flag																	- Grass
			- Mountain																- Pickup (Green Torch)
			- Tor Statue															- Odin Statue
			- Fire																	- Explosion
		4.) [*][3] Main Menu to Stage_One
		5.) [*][2] Introduction Cutscene
		6.) [*][2] Pick Weapon Cutscene
		7.) [*][3] Choose Your Weapon Text
		8.) [*][1] Toss bridgekeeper into the air
		9.) [*][4] Decision UI open and close
		10.)[*][3] Overworld to Underworld
		11.)[*][3] Underworld to Overworld
		12.)[*][2] Healthbar pop up / player takes damage

						------------------------- VISUALS -------------------------
		1.) Rain and Lava particle systems
			- Have a script attached that will follow the player in a way that isn't noticable
		2.) Lightning
			- Will randomly instantiate near the player's location 

						------------------------- SOUND -------------------------

Assets created by me:
	1.) Dialogue background (Green Rectangle)
	2.) Main Menu clouds (5 different sprites)
	3.) Rain Drop Sprite
	4.) Animated Lava particle (Sprite Sheet)


Assets not created by me:
	1.) https://www.dafont.com/theme.php?cat=401	[Font]
	2.) https://hugues-laborde.itch.io/viking-environment-pack-pixel-art	[Viking environment, player, and boss sprites]
	3.) https://hugues-laborde.itch.io/cartoon-viking-character-pack	[Other Viking Sprite]
	4.) https://codemanu.itch.io/pixelart-effect-pack	[Pixelart Effects]
	5.) https://sanctumpixel.itch.io/lightning-lines-pixel-art-effect	[Lightning]
	6.) GothicVania Church Pack	[Unity Asset Store]
	7.) https://opengameart.org/content/blood-particle	[Blood Particle]
	8.) https://weeklyhow.com/how-to-make-a-health-bar-in-unity/	[Healthbar Outline]
	9.) https://elthen.itch.io/2d-pixel-art-portal-sprites [Portal Sprites]
	10.) https://www.zapsplat.com/page/2/?s=thunder&post_type=music&sound-effect-category-id [Designed thunder crack 1/2/3/4]
	11.) https://www.zapsplat.com/music/rain-exterior-street-heavy-pavement-steady/	[Rain sound effect]
	12.) https://www.zapsplat.com/music/rain-water-pour-and-drip-from-roof-into-swimming-pool/	[Other rain sound effect]
	13.) https://www.zapsplat.com/music/football-boot-single-footstep-walk-on-concrete-1/	[Underworld footstep sound effect]
	14.) https://www.zapsplat.com/music/footstep-single-shoe-on-damp-and-dirty-concrete-5/	[Overworld footstep sound effect]
	15.) https://www.zapsplat.com/music/lava-flow/	[Lava sound effect]
	16.) https://www.zapsplat.com/music/campfire-flames-burn-and-sizzle-in-wind/	[Fire sound effect]
	17.) https://elements.envato.com/creature-orc-scream-01-SP57WAP	[Enemy Scream]
	18.) https://elements.envato.com/creature-orc-die-01-6DCFY9M	[Enemy Death]
	19.) https://elements.envato.com/male-scream-8JADKCL	[Player Scream]
	20.) https://www.zapsplat.com/music/heavy-male-scream-out-of-deep-pain-4/	[Player Death]
	21.) https://www.serpentsoundstudios.com/royalty-free-music/celtic-fantasy	[All ambient music]
	22.) https://www.zapsplat.com/music/heavy-medieval-axe-or-other-weapon-swing-in-air-whoosh-4/	[Player Swing]
	23.) https://www.zapsplat.com/music/impact-heavy-object-smash-down/	[Enemy swing]
	24.) https://www.zapsplat.com/music/explosion-large-distant/	[Explosion]
	25.) https://bigsoundbank.com/detail-0477-wilhelm-scream.html	[Wilhelm Scream]
	26.) https://www.techonthenet.com/clipart/keyboard/index.php	[Keyboard keys clip art]
	27.) https://clipground.com/mouse-click-clipart.html	[Mouse clip art]
	28.) https://logomakr.com/2ufAyN	[My icon]

Help from Online Websites, Videos, or Tutorials:
	1.) https://www.youtube.com/watch?v=_nRzoTzeyxU	[Monologue]
	2.) https://docs.unity3d.com/ScriptReference/Vector3.Lerp.html	[Camera Move]
	3.) https://stuartspixelgames.com/2019/02/19/how-to-change-sprites-colour-or-transparency-unity-c/	[Sprite Color Change]
	4.) https://stackoverflow.com/questions/30294216/unity3d-c-sharp-vector3-as-default-parameter	[Vector3 and Quaternion with default parameter (Stage_One Script)]
	5.) https://forum.unity.com/threads/particle-system-2d-rain-effect-how-to-align-particles-with-velocity-tried-many-configurations.817881/	[Rain]
	6.) https://www.highwaynorth.com/blogs/bryan/relative-position-animation-in-unity	[Animation with relative position]
	7.) https://www.youtube.com/watch?v=uZNsc-jWk9g	[VERY ROUGHLY inspired my idea for my DecisionManager script... Emphasis on "ROUGLY inspired"]
	8.) https://gamedev.stackexchange.com/questions/92146/button-stays-highlighted-after-being-clicked-unity3d-4-6-gui [Button stays highlighted after clicking]
	9.) https://forum.unity.com/threads/character-controller-ignores-transform-position.617107/	[Teleporting with Character Controller]
	10.) https://forum.unity.com/threads/coroutines-inside-coroutines.632779/	[Wait for choice to be made inside DecisionManager script]
	11.) http://digitalnativestudios.com/textmeshpro/docs/rich-text/	[Rich text, Pickup item and Activate statue UIs]
	12.) https://dotnetcodr.com/2017/11/15/implementing-an-enumerator-for-a-custom-object-in-net-c-3/	[Using a foreach loop on a custom class, DecisionManager Script]
	13.) https://gyanendushekhar.com/2019/11/17/create-health-bar-unity-3d/	[Healthbar]

Information:
	1.) https://www.bookofthrees.com/monty-python-and-the-holy-grail-bridge-three-questions/	[Monty Python and The Holy Grail, inspiration for the bridge scene of game]
	2.) https://medium.com/human-nature-group/what-is-the-air-speed-velocity-of-an-unladen-swallow-4c17087bbf33	[Inspired one of the choices for one of the bridge choices]


Trouble with this project
	1.) Animations were very tricky at times
		- In specific, getting the x position to be relative, fixed with help of #6 from above^
