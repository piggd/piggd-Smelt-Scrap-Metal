*****************************************
* Mod Name:  piggd Scrap Metal Smelting *
* Author: piggd  						*
* Email: dayzpiggd@gmail.com			*
* Version: 1.0							*
* Date:	04/22/2013						*
*****************************************

Information:
This mod will allow you to smelt tin and soda cans into scarp metal.  It requires fileed canteen of water (boiled or unboiled), # (6 by default) of cans, tool box and a fire. 
The number of cans required can be adjusted from 1 to 11.  11 is max based on canteen requirement and inventory space.

Required:
Camp Fire
Tool Box
Filled Water Canteen ( boiled or unboiled)
# (default 6) of empty Soda to Tin cans

Item: Producted:
Scrap Metal 
Unfilled Water Canteen

Installation:

Unpack your dayz mission pbo.

***************************************
* Copy smelt.sqf  into custom folder. *
***************************************

Make a copy of or modify your existing custom variable.sqf

FIND
	s_player_boil =			-1;

ADD immediately after

// ------------------------------------------------------------------------Piggd Smelt Scrap Metal Start------------------------------------------------------------------------
	s_player_smelt =		-1;
// ------------------------------------------------------------------------Piggd Smelt Scrap Metal End----------------------------------------------------------------------

****************************************
* Modify your fn_self_actions.sqf file *
****************************************

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

// ------------------------------------------------------------------------Piggd Smelt Scrap Metal Start------------------------------------------------------------------------
if (inflamed cursorTarget and _hasToolbox and _canDo) then {
		if (s_player_smelt < 0) then {
			s_player_smelt = player addAction[("<t color=""	#FF9999"">" + ("Smelt Scrap Metal") +"</t>"),"custom\smelt.sqf",cursorTarget, 3 ,true, true,"", ""];
		};
	} else {
		player removeAction s_player_smelt;
		s_player_smelt = -1;
	};
// ------------------------------------------------------------------------Piggd Smelt Scrap Metal Start------------------------------------------------------------------------

