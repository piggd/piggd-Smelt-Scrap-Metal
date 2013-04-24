*****************************************
* Mod Name:  piggd Smel Scrap Metal     *
* Author: piggd							*
* Email: dayzpiggd@gmail.com			*
* Version: 2.0							*
* Date:	04/22/2013						*
*****************************************

Information:
This mod will allow you to smelt tin and soda cans into scarp metal.  It requires fileed canteen of water (boiled or unboiled), # (6 by default) of cans, tool box and a fire. 
The number of cans required can be adjusted from 1 to 11.  11 is max based on canteen requirement and inventory space.

All Required:
Camp Fire
Tool Box
Filled Water Canteen ( boiled or unboiled)

Scrap Metal
Required: 6 empty Soda or Tin cans
Item: Producted: Scrap Metal, Unfilled Water Canteen

Engine Parts
Required: 3 Scrap Meetal
Item: Producted: Engine Parts, Unfilled Water Canteen

Main Rotary Parts
Required: 3 Scrap Meetal
Item: Producted: Main Rotary Parts, Unfilled Water Canteen

Fuel Tank
Required: 2 Scrap Meetal
Item: Producted: Fuel Tank, Unfilled Water Canteen

Wind Screen Glass
Required: 6 Jack Daniel Whisket Bottles
Item: Producted: Wind Screen Glass, Unfilled Water Canteen

Wheel
Required: 1 Scrap Metal, 3 Heat Packs
Item: Producted: Wheel, Unfilled Water Canteen

Jerry Can
Required: 1 Scrap Metal
Item: Producted: Unfilled Jerry Can, Unfilled Water Canteen

Change log ver 1.0 - Inital Script creation
Change log ver 2.0 - Created a new smelt folder.  rename smelt.sqf and move it into the smelt folder.  Created new scripts to smelt Engine Parts, Main Rotary Parts,  Fuel Tank, 
	Wind Screen Glass, Wheel, and Unfilled Jerry Can.

Installation:

Unpack your dayz mission pbo.

*****************************************
* Create a smelt folder 			  	*
* Copy smelt_*.sqf  into smelt folder. *
*****************************************

Make a copy of or modify your existing custom variable.sqf

FIND
	s_player_boil =			-1;

ADD immediately after

// ------------------------------------------------------------------------Piggd Smelt Scrap Metal ver 2.0 Start------------------------------------------------------------------------
	s_player_smelt_scrapmetal =			-1;
	s_player_smelt_engineparts =		-1;
	s_player_smelt_fueltank =			-1;
	s_player_smelt_windscreenglass =	-1;
	s_player_smelt_mainrotoraryparts =	-1;
	s_player_smelt_wheel =				-1;
	s_player_smelt_jerrycan =			-1;
// ------------------------------------------------------------------------Piggd Smelt Scrap Metal ver 2.0 End----------------------------------------------------------------------

*******************************************************************************************************************************
* Modify your fn_self_actions.sqf file, if new rememver to modify your compiles.sql to point to the custom n_self_actions.sqf *
*******************************************************************************************************************************

FIND
	if (inflamed cursorTarget and (_hasbottleitem and _hastinitem) and _canDo) then {
		if (s_player_boil < 0) then {
			s_player_boil = player addAction [localize "str_actions_boilwater", "\z\addons\dayz_code\actions\boil.sqf",cursorTarget, 3, true, true, "", ""];
		};
	} else {
		player removeAction s_player_boil;
		s_player_boil = -1;
	};

ADD immediately after

// ------------------------------------------------------------------------Piggd Smelt Scrap Metal ver 2.0------------------------------------------------------------------------
	// Smelt Scrap Metal
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_scrapmetal < 0) then {
			s_player_smelt_scrapmetal = player addAction[("<t color=""	#FF9999"">" + ("Smelt Scrap Metal") +"</t>"),"smelt\smelt_scrapmetal.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_scrapmetal;
		s_player_smelt_scrapmetal = -1;
	};
	// Smelt Engine Parts
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_engineparts < 0) then {
			s_player_smelt_engineparts = player addAction[("<t color=""	#FF9999"">" + ("Smelt Engine Parts") +"</t>"),"smelt\smelt_engineparts.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_engineparts;
		s_player_smelt_engineparts = -1;
	};
	// Smelt Fuel Tank
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_fueltank < 0) then {
			s_player_smelt_fueltank = player addAction[("<t color=""	#FF9999"">" + ("Smelt Fuel Tank") +"</t>"),"smelt\smelt_fueltank.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_fueltank;
		s_player_smelt_fueltank = -1;
	};
	// Smelt Wind Screen Glass
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_windscreenglass < 0) then {
			s_player_smelt_windscreenglass = player addAction[("<t color=""	#FF9999"">" + ("Smelt Wind Screen Glass") +"</t>"),"smelt\smelt_windscreenglass.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_windscreenglass;
		s_player_smelt_windscreenglass = -1;
	};
	// Smelt Main Rotary Parts
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_mainrotoraryparts < 0) then {
			s_player_smelt_mainrotoraryparts = player addAction[("<t color=""	#FF9999"">" + ("Smelt Main Rotary Parts") +"</t>"),"smelt\smelt_mainrotoraryparts.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_mainrotoraryparts;
		s_player_smelt_mainrotoraryparts = -1;
	};
	// Smelt Wheel
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_wheel < 0) then {
			s_player_smelt_wheel = player addAction[("<t color=""	#FF9999"">" + ("Smelt Wheel") +"</t>"),"smelt\smelt_wheel.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_wheel;
		s_player_smelt_wheel = -1;
	};
	// Smelt Jerry Can
	if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt_jerrycan < 0) then {
			s_player_smelt_jerrycan = player addAction[("<t color=""	#FF9999"">" + ("Smelt Jerry Can") +"</t>"),"smelt\smelt_jerrycan.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt_jerrycan;
		s_player_smelt_jerrycan = -1;
	};

// ------------------------------------------------------------------------Piggd Smelt Scrap Metal ver 2.0 End------------------------------------------------------------------------

Repack your PBO and upload it to the sever.
