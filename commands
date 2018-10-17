const search = require("youtube-search");

var opts = {
  maxResults: 1,
  key: 'AIzaSyA2YG4i9H-4ea1Qv7QD9wphNSez0ReYsbo'
};


module.exports = {
  name:'test',
  async execute(bot,message,args,now){
    search(args.join(' '),opts, (err,Svid) => {

      if(err) {
        message.channel.send("hmmmmmmm something went wrong");
        console.log(err)
        return ;
      }






      let videos = Svid;

      let Svid1 = '';
      for(var i in videos){
        Svid1 += `${videos[i].title}// ${videos[i].link}`;
      }


        let commandFiles = require('./play.js');
        commandFiles.execute(bot,message,[videos[0].link], now).catch(err => console.log(err));

    });
  }
}

module.exports = {
  name:'resume',
  async execute(bot,message,now,args){
    if (!message.member.voiceChannel) return message.reply("You are not in voice channel");

    if(message.member.voiceChannel !== message.guild.me.voiceChannel) return message.reply(`You must be in ***${message.guild.me.voiceChannel.name}*** to Resume`);

    let fetched = now.get(message.guild.id);

    if(!fetched) return message.reply("Sorry there is no song playing right now");

    if(!fetched.dispatcher.paused) return message.reply("This song is not pasued");

    fetched.dispatcher.resume();

    message.reply("Successfully Resumed");
  }
}

module.exports = {
  name:'skip',
  async execute(bot,message,args,now){
    if(!message.member.voiceChannel) return ("You are not in voice channel");

    let fetched = now.get(message.guild.id);

    if(!fetched) return message.reply("Sorry there is no music to skip");

    if(message.member.voiceChannel !== message.guild.me.voiceChannel) return message.reply(`You must be in ***${message.guild.me.voiceChannel.name}*** to skip`);


    now.set(message.guild.id, fetched);

    if (fetched.queue[0]) {
     await message.channel.send('Seccessfully Skipped the Song');
      return fetched.dispatcher.end();
    }

  }
}

const search = require("youtube-search");

var opts = {
  maxResults: 1,
  key: 'AIzaSyA2YG4i9H-4ea1Qv7QD9wphNSez0ReYsbo'
};


module.exports = {
  name:'test',
  async execute(bot,message,args,now){
    search(args.join(' '),opts, (err,Svid) => {

      if(err) {
        message.channel.send("hmmmmmmm something went wrong");
        console.log(err)
        return ;
      }






      let videos = Svid;

      let Svid1 = '';
      for(var i in videos){
        Svid1 += `${videos[i].title}// ${videos[i].link}`;
      }


        let commandFiles = require('./play.js');
        commandFiles.execute(bot,message,[videos[0].link], now).catch(err => console.log(err));

    });
  }
}
module.exports = {
  name: 'pause',
  async execute(bot,message,now,args){
    if (!message.member.voiceChannel) return message.reply("You are not in voice channel");

    if(message.member.voiceChannel !== message.guild.me.voiceChannel) return message.reply(`You must be in ***${message.guild.me.voiceChannel.name}*** to Pause`);

    let fetched = now.get(message.guild.id);

    if(!fetched) return message.channgel.send("Sorry there is no song playing right now!");

    if(fetched.dispatcher.pasued) return message.channel.send("Song is already pasued");

    fetched.dispatcher.pause();

    message.reply("Sucessfully Paused");
  }
}

const Discord = require("discord.js");

module.exports = {
  name: 'help',
  async execute(bot,message,args) {

    let helpEmbed = new Discord.RichEmbed()
    .setAuthor(message.author.username, message.author.avatarURL)
    .setThumbnail(message.author.avatarURL)
    .setColor("#4800ff")
    .addField("#play","Uses to play song by doing #play Youtube link", true)
    .addField("#pause","to freeze music", true)
    .addField("#resume","to resume music", true)
    .addField("#skip","to skip song", true)
    .setFooter("Developed by Jazora#0001");

    message.channel.send(helpEmbed);
  }


}
