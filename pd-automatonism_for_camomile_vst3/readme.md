Those are the files inside pd-automatonism.vst3 structure, for documentation purposes.

Camomile plugins have the following structure :

## Linux : 

[pd-automatonism.vst3]
	[Contents]
		[x86_64-linux]
			-Infos.txt
			-pd-automatonism.pd
			-pd-automatonism.txt
			-pd-automatonism.so
			-(this readme file)
			[patches]
				-Example1.pd
				-Midi-in.pd
				-Playhead.pd
				-(any other patch)
				[automatonism]
					(copy of whole automatonism repository)

## Windows :

[pd-automatonism.vst3]
	-Infos.txt
	-pd-automatonism.pd
	-pd-automatonism.txt
	-pd-automatonism.vst3
	-(this readme file)
		[patches]
		-Example1.pd
		-Midi-in.pd
		-Playhead.pd
		-(any other patch)
		[automatonism]
			(copy of whole automatonism repository)

## Mac OsX

[pd-automatonism.vst3]
	[Contents]
		-Info.plist
		[MacOS]
			-CamomileFx
		[Resources]
			-Infos.txt
			-pd-automatonism.pd
			-pd-automatonism.txt
			-(this readme file)
			[patches]
				-Example1.pd
				-Midi-in.pd
				-Playhead.pd
				-(any other patch)
				[automatonism]
					(copy of whole automatonism repository)