# Unrest Makefile
# Charlotte Koch <dressupgeekout@gmail.com>

SOURCES+=	AlphaImage.cpp
SOURCES+=	AnimationFrame.cpp
SOURCES+=	Caption.cpp
SOURCES+=	ChapterIntro.cpp
SOURCES+=	ClipButton.cpp
SOURCES+=	CreditScreen.cpp
SOURCES+=	DevConsole.cpp
SOURCES+=	EventSeqGroup.cpp
SOURCES+=	EventSequence.cpp
SOURCES+=	FileData.cpp
SOURCES+=	FileMenu.cpp
SOURCES+=	GameEventInfo.cpp
SOURCES+=	GameOverMenu.cpp
SOURCES+=	GameParam.cpp
SOURCES+=	GeneralSettingMenu.cpp
SOURCES+=	GfxSettingMenu.cpp
SOURCES+=	HealthIndicator.cpp
SOURCES+=	HoverInfo.cpp
SOURCES+=	Image.cpp
SOURCES+=	ImageData.cpp
SOURCES+=	ImageManager.cpp
SOURCES+=	Inventory.cpp
SOURCES+=	Item.cpp
SOURCES+=	ItemCollection.cpp
SOURCES+=	ItemMenu.cpp
SOURCES+=	ItemSlot.cpp
SOURCES+=	KeyBindMenu.cpp
SOURCES+=	LevelExit.cpp
SOURCES+=	Line.cpp
SOURCES+=	LoadingScreen.cpp
SOURCES+=	MapData.cpp
SOURCES+=	MapMarkerMenu.cpp
SOURCES+=	ModMenu.cpp
SOURCES+=	MusicArea.cpp
SOURCES+=	MusicManager.cpp
SOURCES+=	OptionMenu.cpp
SOURCES+=	OptionSelect.cpp
SOURCES+=	ParagraphData.cpp
SOURCES+=	PathfindingAgent.cpp
SOURCES+=	PathfindingGraphNode.cpp
SOURCES+=	PathfindingGrid.cpp
SOURCES+=	PauseMenu.cpp
SOURCES+=	PersonHandler.cpp
SOURCES+=	PersonScreen.cpp
SOURCES+=	Polygon.cpp
SOURCES+=	PopUp.cpp
SOURCES+=	ProgressBar.cpp
SOURCES+=	QuestText.cpp
SOURCES+=	Rectangle.cpp
SOURCES+=	ReplyButton.cpp
SOURCES+=	ReplyMenu.cpp
SOURCES+=	ResolutionMenu.cpp
SOURCES+=	SaveGameMenu.cpp
SOURCES+=	ScreenSettings.cpp
SOURCES+=	SectionHeader.cpp
SOURCES+=	Shape.cpp
SOURCES+=	SlideShow.cpp
SOURCES+=	SpriteConstant.cpp
SOURCES+=	Stairs.cpp
SOURCES+=	Stat.cpp
SOURCES+=	StatDrawHelper.cpp
SOURCES+=	StatPreview.cpp
SOURCES+=	StatTemplate.cpp
SOURCES+=	StateButton.cpp
SOURCES+=	TMXLayer.cpp
SOURCES+=	TMXMap.cpp
SOURCES+=	TMXTileSet.cpp
SOURCES+=	TextManager.cpp
SOURCES+=	ToggleButton.cpp
SOURCES+=	TraitButton.cpp
SOURCES+=	TraitMenu.cpp
SOURCES+=	XMLDoc.cpp
SOURCES+=	animation.cpp
SOURCES+=	animframe.cpp
SOURCES+=	animset.cpp
SOURCES+=	app.cpp
SOURCES+=	button.cpp
SOURCES+=	collision.cpp
SOURCES+=	color.cpp
SOURCES+=	conversationdata.cpp
SOURCES+=	cursor.cpp
SOURCES+=	dialogbox.cpp
SOURCES+=	effect.cpp
SOURCES+=	element.cpp
SOURCES+=	emotion.cpp
SOURCES+=	eventstore.cpp
SOURCES+=	fightanim.cpp
SOURCES+=	fightinput.cpp
SOURCES+=	fightmove.cpp
SOURCES+=	fightmoves.cpp
SOURCES+=	filesystem.cpp
SOURCES+=	game.cpp
SOURCES+=	gameevent.cpp
SOURCES+=	gameeventmanager.cpp
SOURCES+=	hotkey.cpp
SOURCES+=	hud.cpp
SOURCES+=	imageeffect.cpp
SOURCES+=	input.cpp
SOURCES+=	inputval.cpp
SOURCES+=	journal.cpp
SOURCES+=	level.cpp
SOURCES+=	level_ai.cpp
SOURCES+=	level_collide.cpp
SOURCES+=	level_draw.cpp
SOURCES+=	level_load.cpp
SOURCES+=	level_objects.cpp
SOURCES+=	loaders.cpp
SOURCES+=	main.cpp
SOURCES+=	mainmenu.cpp
SOURCES+=	map.cpp
SOURCES+=	moveeffect.cpp
SOURCES+=	movement.cpp
SOURCES+=	opinion.cpp
SOURCES+=	person.cpp
SOURCES+=	personbase.cpp
SOURCES+=	quest.cpp
SOURCES+=	questmenu.cpp
SOURCES+=	slider.cpp
SOURCES+=	splash.cpp
SOURCES+=	sprite.cpp
SOURCES+=	spriteai.cpp
SOURCES+=	stdafx.cpp
SOURCES+=	talknotify.cpp
SOURCES+=	textarea.cpp
SOURCES+=	textdata.cpp
SOURCES+=	timer.cpp
SOURCES+=	trait.cpp
SOURCES+=	trigger.cpp
SOURCES+=	triggerset.cpp
SOURCES+=	url.cpp
SOURCES+=	walkframes.cpp

OBJS=		$(patsubst %.cpp,%.o,$(SOURCES))
CLEANFILES+=	$(OBJS)

PROG=		unrest

# SDL2
CXXFLAGS+=	$(shell sdl2-config --cflags)
LDFLAGS+=	$(shell sdl2-config --libs)
LDFLAGS+=	-lSDL2_ttf
LDFLAGS+=	-lSDL2_mixer
LDFLAGS+=	-lSDL2_image

# Boost
BOOST_CXXFLAGS?=	# defined
BOOST_LDFLAGS?=		# defined
CXXFLAGS+=		$(BOOST_CXXFLAGS)
LDFLAGS+=		$(BOOST_LDFLAGS) -lboost_filesystem

# Extra compiler flags
CXXFLAGS+=	$(EXTRA_CXXFLAGS)

# Installation options
DESTDIR?=	# defined
PREFIX?=	/usr/local
BINDIR?=	bin

.PHONY: all
all: $(PROG)

CLEANFILES+=	$(PROG)
$(PROG): $(OBJS)
	$(CXX) -o $@ $^ $(LDFLAGS)

.cpp.o:
	$(CXX) -c $(CXXFLAGS) -o $@ $<

.PHONY: install
install: $(PROG)
	install -d $(DESTDIR)$(PREFIX)/$(BINDIR)
	install -m0755 $(PROG) $(DESTDIR)$(PREFIX)/$(BINDIR)

.PHONY: clean
clean:
	rm -f $(CLEANFILES) *.core
