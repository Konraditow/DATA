#! /path/to/executable/eggdrop
loadmodule pbkdf2    ; # Generation 2 userfile encryption
loadmodule blowfish  ; # Legacy userfile encryption support
loadmodule channels  ; # Channel support
loadmodule server    ; # Core server support
loadmodule ctcp      ; # CTCP functionality
loadmodule irc       ; # Basic IRC functionality
#loadmodule transfer ; # DCC SEND/GET and Userfile transfer
#loadmodule share    ; # Userfile sharing
#loadmodule compress ; # Compress userfiles for transfer
#loadmodule filesys  ; # File server support
loadmodule notes     ; # Note storing for users
loadmodule console   ; # Console setting storage
loadmodule seen     ; # Basic seen functionality
#loadmodule assoc    ; # Party line channel naming
loadmodule uptime    ; # Centralized uptime stat collection (http://uptime.eggheads.org)
loadmodule ident    ; # Ident support
#loadmodule twitch   ; # Twitch gaming service support

set nick "web0s"
set altnick "web?s"
set realname "web0s"
set username "web0s"
set pidfile "pid.eggdrop"
set admin "Konrado"
set network "undernet"
set owner "Konrado"
server add irc.undernet.org 6667
#server add another.example.com 6669 password
#server add 2001:db8:618:5c0:263:: 6669 password
#server add ssl.example.net +7000
#set vhost4 "virtual.host.com"
set vhost4 "206.41.113.95"
#set vhost6 "KONRADO.PRO"
#set vhost6 "206.41.113.95"
set notify-newusers "$owner"



# Set the ident method you wish to use. Each of these methods requires
# some form of external configuration in order to function. See
# doc/settings/mod.ident for additional information.
# Options are:
#   0 = oidentd
#         Your bot will overwrite $HOME/.oidentd.conf right before opening the
#         socket to the IRC server with the global reply.
#         NOTE: requires the oidentd service to be running on the host machine
#   1 = Builtin
#         Your bot will automatically turn its builtin identd on and off when
#         needed so it shouldn't conflict with other identds that do the same.
#         NOTE: Eggdrop must be granted permissions on the host system to bind
#         to port 113. 
set ident-method 0

# Set the ident port to use for ident-method 1.
#set ident-port 113

# Some IRC servers are using some non-standard op-like channel prefixes/modes.
# Define them here so the bot can recognize them. Just "@" should be fine for
# most networks. Un-comment the second line for some UnrealIRCds.

set opchars "@"
#set opchars "@&~"

####
set default-flood-chan 15:60
set default-flood-deop 3:10
set default-flood-kick 3:10
set default-flood-join 5:60
set default-flood-ctcp 3:60
set default-flood-nick 5:60
set default-aop-delay 5:30
set default-idle-kick 0
set default-chanmode "nt"
set default-stopnethack-mode 0
set default-revenge-mode 0
set default-ban-type 3
set default-ban-time 120
set default-exempt-time 60
set default-invite-time 60

set default-chanset {
        -autoop         -autovoice
        -bitch          +cycle
        +dontkickops    +dynamicbans
        +dynamicexempts +dynamicinvites
        -enforcebans    +greet
        -inactive       -nodesynch
        -protectfriends +protectops
        -revenge        -revengebot
        -secret         -seen
        +shared         -statuslog
        +userbans       +userexempts
        +userinvites    -protecthalfops
        -autohalfop     -static
}
# chanmode +/-<modes>
#    This setting makes the bot enforce channel modes. It will always add
#    the +<modes> and remove the -<modes> modes.
#
# idle-kick 0
#    This setting will make the bot check every minute for idle
#    users. Set this to 0 to disable idle check.
#
# stopnethack-mode 0
#    This setting will make the bot de-op anyone who enters the channel
#    with serverops. There are seven different modes for this settings:
#      0 turn off
#      1 isoptest (allow serverop if registered op)
#      2 wasoptest (allow serverop if op before split)
#      3 allow serverop if isop or wasop
#      4 allow serverop if isop and wasop.
#      5 If the channel is -bitch, see stopnethack-mode 3
#        If the channel is +bitch, see stopnethack-mode 1
#      6 If the channel is -bitch, see stopnethack-mode 2
#        If the channel is +bitch, see stopnethack-mode 4
#
# revenge-mode 0
#   This settings defines how the bot should punish bad users when
#   revenging. There are four possible settings:
#     0 Deop the user.
#     1 Deop the user and give them the +d flag for the channel.
#     2 Deop the user, give them the +d flag for the channel, and kick them.
#     3 Deop the user, give them the +d flag for the channel, kick, and ban them.
#
# ban-type 3
#   This setting defines what type of bans should eggdrop place for +k users or
#   when revenge-mode is 3.
#   Available types are:
#     0 *!user@host
#     1 *!*user@host
#     2 *!*@host
#     3 *!*user@*.host
#     4 *!*@*.host
#     5 nick!user@host
#     6 nick!*user@host
#     7 nick!*@host
#     8 nick!*user@*.host
#     9 nick!*@*.host
#   You can also specify types from 10 to 19 which correspond to types
#   0 to 9, but instead of using a * wildcard to replace portions of the
#   host, only numbers in hostnames are replaced with the '?' wildcard.
#   Same is valid for types 20-29, but instead of '?', the '*' wildcard
#   will be used. Types 30-39 set the host to '*'.
#
# ban-time 120
#   Set here how long temporary bans will last (in minutes). If you
#   set this setting to 0, the bot will never remove them.
#
# exempt-time 60
#   Set here how long temporary exempts will last (in minutes). If you
#   set this setting to 0, the bot will never remove them. The bot will
#   check the exempts every X minutes, but will not remove the exempt if
#   a ban is set on the channel that matches that exempt. Once the ban is
#   removed, then the exempt will be removed the next time the bot checks.
#   Please note that this is an IRCnet feature.
#
# invite-time 60
#   Set here how long temporary invites will last (in minutes). If you
#   set this setting to 0, the bot will never remove them. The bot will
#   check the invites every X minutes, but will not remove the invite if
#   a channel is set to +i. Once the channel is -i then the invite will be
#   removed the next time the bot checks. Please note that this is an IRCnet
#   feature.
#
# aop-delay (minimum:maximum)
# This is used for autoop, autohalfop, autovoice. If an op or voice joins a
# channel while another op or voice is pending, the bot will attempt to put
# both modes on one line.
#   aop-delay 0   No delay is used.
#   aop-delay X   An X second delay is used.
#   aop-delay X:Y A random delay between X and Y is used.
#
# need-op { putserv "PRIVMSG #lamest :op me cos i'm lame!" }
#    This setting will make the bot run the script enclosed in brackets
#    if it does not have ops. This must be shorter than 120 characters.
#    If you use scripts like getops.tcl or botnetop.tcl, you don't need
#    to set this setting.
#
# need-invite { putserv "PRIVMSG #lamest :let me in!" }
#    This setting will make the bot run the script enclosed in brackets
#    if it needs an invite to the channel. This must be shorter than 120
#    characters. If you use scripts like getops.tcl or botnetop.tcl, you
#    don't need to set this setting.
#
# need-key { putserv "PRIVMSG #lamest :let me in!" }
#    This setting will make the bot run the script enclosed in brackets
#    if it needs the key to the channel. This must be shorter than 120
#    characters. If you use scripts like getops.tcl or botnetop.tcl, you
#    don't need to set this setting
#
# need-unban { putserv "PRIVMSG #lamest :let me in!" }
#    This setting will make the bot run the script enclosed in brackets
#    if it needs to be unbanned on the channel. This must be shorter than
#    120 characters. If you use scripts like getops.tcl or botnetop.tcl,
#    you don't need to set this setting
#
# need-limit { putserv "PRIVMSG #lamest :let me in!" }
#    This setting will make the bot run the script enclosed in brackets
#    if it needs the limit to be raised on the channel. This must be
#    shorter than 120 characters. If you use scripts like getops.tcl or
#    botnetop.tcl, you don't need to set this setting
#
# flood-chan 15:60
#    Set here how many channel messages in how many seconds from one
#    host constitutes a flood. Setting this to 0, 0:X or X:0 disables
#    flood protection for the channel, where X is an integer >= 0.
#
# flood-deop 3:10
#    Set here how many deops in how many seconds from one host constitutes
#    a flood. Setting this to 0, 0:X or X:0 disables deop flood protection
#    for the channel, where X is an integer >= 0.
#
# flood-kick 3:10
#    Set here how many kicks in how many seconds from one host constitutes
#    a flood. Setting this to 0, 0:X or X:0 disables kick flood protection
#    for the channel, where X is an integer >= 0.
#
# flood-join 5:60
#    Set here how many joins in how many seconds from one host constitutes
#    a flood. Setting this to 0, 0:X or X:0 disables join flood protection
#    for the channel, where X is an integer >= 0.
#
# flood-ctcp 3:60
#    Set here how many channel ctcps in how many seconds from one host
#    constitutes a flood. Setting this to 0, 0:X or X:0 disables ctcp flood
#    protection for the channel, where X is an integer >= 0.
#
# flood-nick 5:60
#    Set here how many nick changes in how many seconds from one host
#    constitutes a flood. Setting this to 0, 0:X or X:0 disables nick flood
#    protection for the channel, where X is an integer >= 0.
#
# A complete list of all available channel settings:
#
# enforcebans
#    When a ban is set, kick people who are on the channel and match
#    the ban?
#
# dynamicbans
#    Only activate bans on the channel when necessary? This keeps
#    the channel's ban list from getting excessively long. The bot
#    still remembers every ban, but it only activates a ban on the
#    channel when it sees someone join who matches that ban.
#
# userbans
#    Allow bans to be made by users directly? If turned off, the bot
#    will require all bans to be made through the bot's console.
#
# dynamicexempts
#    Only activate exempts on the channel when necessary? This keeps
#    the channel's exempt list from getting excessively long. The bot
#    still remembers every exempt, but it only activates a exempt on
#    the channel when it sees a ban set that matches the exempt. The
#    exempt remains active on the channel for as long as the ban is
#    still active.
#
# userexempts
#    Allow exempts to be made by users directly? If turned off, the
#    bot will require all exempts to be made through the bot's console.
#
# dynamicinvites
#    Only activate invites on the channel when necessary? This keeps
#    the channel's invite list from getting excessively long. The bot
#    still remembers every invite, but the invites are only activated
#    when the channel is set to invite only and a user joins after
#    requesting an invite. Once set, the invite remains until the
#    channel goes to -i.
#
# userinvites
#    Allow invites to be made by users directly? If turned off, the
#    bot will require all invites to be made through the bot's console.
#
# autoop
#    Op users with the +o flag as soon as they join the channel?
#    This is insecure and not recommended.
#
# autohalfop
#    Halfop users with the +l flag as soon as they join the channel?
#    This is insecure and not recommended.
#
# bitch
#    Only let users with +o) flag be opped on the channel?
#
# greet
#    Say a user's info line when they join the channel?
#
# protectops
#    Re-op a user with the +o flag if they get deopped?
#
# protecthalfops
#    Re-halfop a user with the +l flag if they get dehalfopped?
#
# protectfriends
#    Re-op a user with the +f flag if they get deopped?
#
# statuslog
#    Log the channel status line every 5 minutes? This shows the bot's
#    status on the channel (op, voice, etc.), the channel's modes, and
#    the total number of members, ops, voices, regular users, and +b,
#    +e, and +I modes on the channel. A sample status line follows:
#
#      [01:40] @#lamest (+istn) : [m/1 o/1 v/4 n/7 b/1 e/5 I/7]
#
# revenge
#    Remember people who deop/kick/ban the bot, valid ops, or friends
#    and punish them? Users with the +f flag are exempt from revenge.
#
# revengebot
#    This is similar to to the 'revenge' option, but it only triggers
#    if a bot gets deopped, kicked or banned.
#
# autovoice
#    Voice users with the +v flag when they join the channel?
#
# secret
#    Prevent this channel from being listed on the botnet?
#
# shared
#    Share channel-related user info for this channel?
#
# cycle
#    Cycle the channel when it has no ops?
#
# dontkickops
#    Do you want the bot not to be able to kick users who have the +o
#    flag, letting them kick-flood for instance to protect the channel
#    against clone attacks.
#
# inactive
#    This prevents the bot from joining the channel (or makes it leave
#    the channel if it is already there). It can be useful to make the
#    bot leave a channel without losing its settings, channel-specific
#    user flags, channel bans, and without affecting sharing.
#
# seen
#    Respond to seen requests in the channel?  The seen module must be
#    loaded for this to work.
#
# nodesynch
#    Allow non-ops to perform channel modes? This can stop the bot from
#    fighting with services such as ChanServ, or from kicking IRCops when
#    setting channel modes without having ops.
#
# static
#    Allow only permanent owners to remove the channel?

# To add a channel to eggdrop, please enter the bot's partyline and type
# .+chan #channel. Check also .help chanset and .help chaninfo.
# You can still add a channel here and it will be saved if you have a
# chanfile. We recommend you to use the partyline though.




## If you have a NAT firewall, enter your outside IP here. This IP
## is used for transfers and CTCP replies only, and is different than the
## vhost4/6 settings. You likely still need to set them.
set nat-ip "192.99.68.10"

## If you want all dcc file transfers to use a particular portrange either
## because you're behind a firewall, or for other security reasons, set it
## here.
set reserved-portrange 2010:2020

## Prefer IPv6 over IPv4 for connections and dns resolution?
## If the preferred protocol family is not supported, the other one
## will be tried.
set prefer-ipv6 0

## If you want to have your Eggdrop messages displayed in a language other
## than English, change this setting to match your preference. An alternative
## would be to set the environment variable EGG_LANG to that value.
##
## Languages included with Eggdrop: Danish, English, French, Finnish, German,
## Italian, Portuguese.
#addlang "english"

##### LOG FILES #####

## See eggdrop.conf for documentation on the logfile flags and settings.

# This creates a logfile named eggdrop.log that captures items logged at the
# m, c, and o log levels (private msgs/ctcps, commands/errors, and misc 
# info) from any channel.
logfile msbxco * "logs/eggdrop.log"

# This creates a logfile named lamest.log that captures items logged at the
# j, p, and k log levels (joins/parts/quits/netsplits, public chat,
# kicks/bans/mode changes) on the channel #lamest.
logfile jpkn * "logs/eggdrop.log"

## This should be 0 for disk space restricted shells, and 1 if you want to
## generate channel statistics with tools such as pisg.
## If it is 0, eggdrop will delete logfiles older than 2 days.
## If it is 1, eggdrop will keep logging into the specified logfiles forever.
## See eggdrop.conf for more detailed settings.
set log-forever 1

## Code to set settings based on the above setting, do not edit this.
if {${log-forever}} {
	set switch-logfiles-at 2500
	set keep-all-logs 0
}

## "Writing user file..." and "Writing channel file..." messages won't be logged
## anymore if this option is enabled. If you set it to 2, the "Backing up user
## file..." and "Backing up channel file..." messages will also not be logged.
## In addition to this, you can disable the "Switching logfiles..." and the new
## date message at midnight, by setting this to 3.
set quiet-save 0

##### FILES AND DIRECTORIES #####

# Specify here the filename your userfile should be saved as.
set userfile "eggdrop.user"

# Specify here where Eggdrop should look for help files. Don't modify this
# setting unless you know what you're doing!
set help-path "help/"

##### BOTNET/DCC/TELNET #####

## If you want to use a different nickname on the botnet than you use on
## IRC (i.e. if you're on an un-trusted botnet), un-comment the next line
## and set it to the nick you would like to use.
set botnet-nick "web0s"

# This opens a telnet port by which you and other bots can interact with the
# Eggdrop by telneting in. There are more options for the listen command in
# doc/tcl-commands.doc. Note that if you are running more than one bot on the
# same machine, you will want to space the telnet ports at LEAST 5 apart,
# although 10 is even better.
#
# Valid ports are typically anything between 1025 and 65535 assuming the
# port is not already in use. If you would like the bot to listen for users
# and bots in separate ports, use the following format:
#
#   listen 3333 bots
#   listen 4444 users
#
# If you wish to use only one port, use this format:
#
#   listen 3333 all
#
# You can setup a SSL port by prepending a plus sign to it:
#
#   listen +5555 all
#
# To bind the listening port to a specific IP instead of all available, insert
# a valid IP assigned to the host Eggdrop is running on in front of the port
# (this replaces the listen-addr setting used prior to Eggdrop v1.9)
#
#   listen 1.2.3.4 3333 all
#
# You need to un-comment this line and change the port number in order to open
# the listen port. You should not keep this set to 3333.
listen 3333 all
set telnet-banner "text/banner"
set motd "text/motd"
set text-path "text/"
# This setting will drop telnet connections not matching a known host.
set protect-telnet 0
set ident-timeout 5
# If stealth-telnets is 1, the string in this setting will replace the
# traditional Eggdrop banner. Two common choices are listed. (The \n's are
# present to maintain backwards compatibility and will be removed in a
# future release)
#set stealth-prompt "login: "
set stealth-prompt "\n\nNickname.\n"


# This specifies what permissions the user, channel, and notes files should
# be set to. The octal values are the same as for the chmod system command.
#
# To remind you:
#
#          u  g  o           u  g  o           u  g  o
#    0600  rw-------   0400  r--------   0200  -w-------    u - user
#    0660  rw-rw----   0440  r--r-----   0220  -w--w----    g - group
#    0666  rw-rw-rw-   0444  r--r--r--   0222  -w--w--w-    o - others
#
# Note that the default 0600 is the most secure one and should only be changed
# if you need your files for shell scripting or other external applications.
set userfile-perm 0600
##### SSL SETTINGS #####

## Settings in this section take effect when eggdrop is compiled with TLS
## support. If you didn't generate SSL keys already, you can type 
## 'make sslcert' in your eggdrop source directory.
##
## IMPORTANT: The following two settings MUST be uncommented in order to
## use SSL functionality!
#set ssl-privatekey "eggdrop.key"

## Specify the filename where your SSL certificate is located. If you
## don't set this, eggdrop will not be able to act as a server in SSL
## connections. Must be in PEM format.
#set ssl-certificate "eggdrop.crt"

## Specify the location at which CA certificates for verification purposes
## are located. These certificates are trusted. If you don't set this,
## certificate verification will not work.
set ssl-capath "/etc/ssl/"

## Enable certificate authorization. Set to 1 to allow users and bots to
## identify automatically by their certificate fingerprints. Setting it
## to 2 to will force fingerprint logins. With a value of 2, users without
## a fingerprint set or with a certificate UID not matching their handle
## won't be allowed to login on SSL enabled telnet ports. Fingerprints
## must be set in advance with the .fprint and .chfinger commands.
## NOTE: this setting has no effect on plain-text ports.
#set ssl-cert-auth 0

## You can control SSL certificate verification using the following variables.
## All of them are flag-based. You can set them by adding together the numbers
## for all exceptions you want to enable. By default certificate verification
## is disabled and all certificates are assumed to be valid. The numbers are
## the following:
##
## Enable certificate verification - 1
## Allow self-signed certificates - 2
## Don't check peer common or alt names - 4
## Allow expired certificates - 8
## Allow certificates which are not valid yet - 16
## Allow revoked certificates - 32
## A value of 0 disables verification.

## Control certificate verification for IRC servers
#set ssl-verify-server 0

## Control certificate verification for DCC chats (only /dcc chat botnick)
#set ssl-verify-dcc 0

## Control certificate verification for linking to hubs
#set ssl-verify-bots 0

## Control certificate verification for SSL listening ports. This includes
## leaf bots connecting, users telneting in and /ctcp bot chat.
#set ssl-verify-clients 0


##### COMMON MODULES SETTINGS #####

## Below are various settings for the modules included with Eggdrop.
## PLEASE READ AND EDIT THEM CAREFULLY, even if you're an old hand at
## Eggdrop, things change.

## This path specifies the path were Eggdrop should look for its modules.
## If you run the bot from the compilation directory, you will want to set
## this to "". If you use 'make install' (like all good kiddies do ;), this
## is a fine default. Otherwise, use your head :)
#set mod-path "modules-1.9.2/"

#### CHANNELS MODULE ####

## Enter here the filename where dynamic channel settings are stored.
set chanfile "eggdrop.chan"

#### SERVER MODULE ####

## What is your network?
##   If your network is not specifically listed here, please see eggdrop.conf
##   for more information on what the best selection is.
## Options are:
##   EFnet
##   IRCnet
##   Undernet
##   DALnet
##   Libera
##   freenode
##   QuakeNet
##   Rizon
##   Twitch (This requires twitch.mod to be loaded as well)
##   Other (This is a good, sane option if your network/ircd is not listed here)
set net-type "Undernet"

# This is a Tcl script to be run immediately after connecting to a server. If
# you want to authenticate Eggdrop with NickServ, uncomment and edit the middle
# line below.
bind evnt - init-server evnt:init_server

proc evnt:init_server {type} {
  global botnick
  putquick "MODE $botnick +ibR-ws"
              putserv "MODE $botnick +xBRtipb-ws"
                putserv "ignore -r"
#  putserv "PRIVMSG NickServ :identify <password>"
}

## Set the default port which should be used if none is specified with
## '.jump' or in 'set servers'.
set default-port 6667

## This setting allows you to specify the maximum nick-length supported by your
## network. The default setting is 9. The maximum supported length by Eggdrop
## is 32.
#set nick-len 9

#### CTCP MODULE ####

## Set here how the ctcp module should answer ctcps.
## Options are:
##   0 = Normal behavior is used.
##   1 = The bot ignores all ctcps, except for CHAT and PING requests
##       by users with the +o flag.
##   2 = Normal behavior is used, however the bot will not answer more
##       than X ctcps in Y seconds (defined by 'set flood-ctcp').
set ctcp-mode 0

#### IRC MODULE ####

## Many takeover attempts occur due to lame users blindly /msg ident'ing to
## the bot and attempting to guess passwords. We now unbind this command by
## default to discourage them. You can enable these commands by commenting the
## following two lines.
#unbind msg - mirc *msg:hello 
unbind msg - ident *msg:ident
unbind msg - addhost *msg:addhost

#### NOTES MODULE ####

## Set here the filename where private notes between users are stored.
set notefile "eggdrop.notes"

##### SCRIPTS #####

## This is a good place to load scripts to use with your bot.

## This line loads script.tcl from the scripts directory inside your Eggdrop's
## directory. All scripts should be put there, although you can place them where
## you like as long as you can supply a fully qualified path to them.
##
## source scripts/script.tcl The 3 scripts below are default and shouldn't be removed.

loadhelp userinfo.help
source scripts/alltools.tcl
source scripts/action.fix.tcl
source scripts/dccwhois.tcl
source scripts/userinfo.tcl
source X/win.tcl





















## Use this script for Tcl and Eggdrop backwards compatibility.
## NOTE: This can also cause problems with some newer scripts.
#source scripts/compat.tcl

## This next line checks if eggdrop is being executed from the source directory, do not remove it
if {[file exists aclocal.m4]} { die {You are attempting to run Eggdrop from the source directory. Please finish installing Eggdrop by running "make install" and run it from the install location.} }

## A few IRC networks (EFnet and Undernet) have added some simple checks to
## prevent drones from connecting to the IRC network. While these checks are
## fairly trivial, they will prevent your Eggdrop from automatically
## connecting. In an effort to work-around these, we have developed a couple of
## TCL scripts to automate the process.

if {[info exists net-type]} {
  switch -- ${net-type} {
    "EFnet" {
      # EFnet
      source scripts/quotepong.tcl
    }
    "0" {
      # EFnet
      source scripts/quotepong.tcl
    }
  }
}
