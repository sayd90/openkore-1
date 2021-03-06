Version 7

alertSound($event)
$event: unique event name

Plays a sound if plugin alertSound is enabled (see sys.txt), and if a sound is specified for the event.

The config option "alertSound_#_eventList" should have a comma seperated list of all the desired events.

Supported events:
	death, emotion, teleport, map change, monster <monster name>, player <player name>, player *, GM near, avoidGM_near,
	avoidList_near, private GM chat, private avoidList chat (not working for ID), private chat, public GM chat, public avoidList chat,
	public npc chat, public chat, system message, disconnected, item <item name>, item <item ID>, item cards, item *<part item name>*

example config.txt:

alertSound {
	eventList public GM chat
	play plugins\alertSound\sounds\alarm.wav
	disabled 0
	notInTown 0
	inLockOnly 0
	# other Self Conditions
}
alertSound {
	eventList private chat
	play plugins\alertSound\sounds\chicken.wav
	disabled 0
	notInTown 0
	inLockOnly 0
	# other Self Conditions
}
alertSound {
	eventList private avoidList chat, public avoidList chat
	play plugins\alertSound\sounds\rooster.wav
	disabled 0
	notInTown 0
	inLockOnly 0
}

alertSound {
	eventList death, disconnected
	play plugins\alertSound\sounds\warning.wav
	disabled 0
	notInTown 0
	inLockOnly 0
	# other Self Conditions
}
alertSound {
	eventList monster Poring, player 4epT
	disabled 1
	play plugins\alertSound\sounds\birds.wav
	notInTown 1
	inLockOnly 1
	# other Self Conditions
}
alertSound {
	eventList teleport, public chat, emotion
	notInTown 1
	inLockOnly 0
	disabled 0
	play plugins\alertSound\sounds\birds.wav
	# other Self Conditions
}
alertSound {
	eventList private GM chat, map change
	play plugins\alertSound\sounds\alarm.wav
	disabled 0
	notInTown 0
	inLockOnly 0
	# other Self Conditions
}
alertSound {
	eventList item Jellopy, item Red Potion, item cards, item *Card*, item *potion*
	play SystemDefault
	disabled 1
	notInTown 0
	inLockOnly 0
	# other Self Conditions
}
alertSound {
	eventList avoidList_near
	play plugins\alertSound\sounds\beep.wav
	disabled 0
	notInTown 1
	timeout 5
}