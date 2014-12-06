(function () {

    function extend('https://github.com/MadTrap/MadTrap/blob/master/README.md')

        
        if (!window.bot) {
            return setTimeout(extend, 1 * 1000);
        }

        var bot = window.bot;

        bot.retrieveSettings();

        bot.commands.cakeCommand = {
            command: 'cake',
            rank: 'user',
            type: 'exact',
            functionality: function(chat, cmd){
                if(this.type === 'exact' && chat.message.length !== cmd.length) return void (0);
                if( !bot.commands.executable(this.rank, chat) ) return void (0);
                else {
                    API.sendChat("/me Bacon!!!");
                }
            }
        };

        bot.commands.baconCommand = {
            command: 'bacon',  //The command to be called. With the standard command literal this would be: !bacon
            rank: 'user', //Minimum user permission to use the command
            type: 'exact', //Specify if it can accept variables or not (if so, these have to be handled yourself through the chat.message
            functionality: function (chat, cmd) {
                if (this.type === 'exact' && chat.message.length !== cmd.length) return void (0);
                if (!bot.commands.executable(this.rank, chat)) return void (0);
                else {
                    API.sendChat("/me Bacon!!!");
                }
            }
        };

        bot.loadChat('https://rawgit.com/Yemasthui/basicBot/master/lang/en.json');

    }

    localStorage.setItem("basicBotsettings", JSON.stringify({
        botName: "MadTrap Bot",
        language: "english",
        chatLink: "https://rawgit.com/Yemasthui/basicBot/master/lang/en.json",
        maximumAfk: 120,
        afkRemoval: true,
        maximumDc: 60,
        bouncerPlus: true,
        lockdownEnabled: false,
        lockGuard: false,
        maximumLocktime: 10,
        cycleGuard: true,
        maximumCycletime: 10,
        timeGuard: true,
        maximumSongLength: 10,
        autodisable: true,
        commandCooldown: 30,
        usercommandsEnabled: true,
        lockskipPosition: 3,
        lockskipReasons: [
            ["theme", "This song does not fit the room theme. "],
            ["op", "This song is on the OP list. "],
            ["history", "This song is in the history. "],
            ["mix", "You played a mix, which is against the rules. "],
            ["sound", "The song you played had bad sound quality or no sound. "],
            ["nsfw", "The song you contained was NSFW (image or sound). "],
            ["unavailable", "The song you played was not available for some users. "]
        ],
        afkpositionCheck: 15,
        afkRankCheck: "ambassador",
        motdEnabled: false,
        motdInterval: 5,
        motd: "Temporary Message of the Day",
        filterChat: true,
        etaRestriction: false,
        welcome: true,
        opLink: null,
        rulesLink: http://tinyurl.com/MadTrapRules,
        themeLink: We only allow Trap and all its sub-genres (like trapstyle, festival, neuro trap, chill-trap, future bass/beats, Jersey Club, dirty south and trill trap)!,
        fbLink: null,
        youtubeLink: https;//youtube.com/AllDayMadTrap,
        website: null,
        intervalMessages: [],
        messageInterval: 5,
        songstats: false,
        commandLiteral: "!",
        
        }
    }));

    $.getScript('https://rawgit.com/Yemasthui/basicBot/master/basicBot.js', 'https://github.com/MadTrap/MadTrap/blob/master/README.md');

}).call(this);
