### Introducton

This is a free, none commercial community package that allows to communicate with the public blizzard wow web api in an abstract way. Community package means, that this package is developed for the community and by my selfe without any profit.

Please read the "Legal Faq" from the bilzzard homepage first before you use this package: [Blizzard Legal FAQ](http://eu.blizzard.com/en-gb/company/about/legal-faq.html)

This means not, that this package is restricted from blizzard, but be careful with their rights to avoid any misunderstoods.

Notice that blizzard have a request limit in their api. If you need a higher limit you have to register your application here: [dev.battle.net](https://dev.battle.net/) and offer an authoriziation key.

### Features

There are all Api calls from the official web api documentation implemented. See there for more informations:

[blizzard.github.io/api-wow-docs](http://blizzard.github.io/api-wow-docs/)

**Complete Call Example:**
<pre><code class="php">
include_once './wow/region.php';
include_once './wow.php';

$region = new jpWoWRegion('europe', 'de_DE');
$wow = new jpWoW($region);

$charName = 'Your character name';
$realm = 'Realm';
$guildName = 'Your guild name';

$wow->getAchievment(2144);
$wow->getAuction($realm);
$wow->getBattlePetAbility(640);
$wow->getBattlePetSpecies(258);
$wow->getBattlePetStats(258,25,5,4);
$wow->getChallangeMode($realm);
$wow->getCharacter($charName, $realm);
$wow->getCharacterAllFields($charName, $realm);
$wow->getCharacterAchievements($charName, $realm);
$wow->getCharacterAppearance($charName, $realm);
$wow->getCharacterFeed($charName, $realm);
$wow->getCharacterGuild($charName, $realm);
$wow->getCharacterHunterPets($charName, $realm);
$wow->getCharacterItems($charName, $realm);
$wow->getCharacterMounts($charName, $realm);
$wow->getCharacterPets($charName, $realm);
$wow->getCharacterPetSlots($charName, $realm);
$wow->getCharacterProfessions($charName, $realm);
$wow->getCharacterProgression($charName, $realm);
$wow->getCharacterPvp($charName, $realm);
$wow->getCharacterQuests($charName, $realm);
$wow->getCharacterReputation($charName, $realm);
$wow->getCharacterStats($charName, $realm);
$wow->getCharacterTalents($charName, $realm);
$wow->getCharacterTitles($charName, $realm);
$wow->getCharacterAudit($charName, $realm);
$wow->getItem(18803);
$wow->getItemSet(1060);
$wow->getGuild($guildName, $realm);
$wow->getGuildAllFields($guildName, $realm)
$wow->getGuildMembers('$guildName', $realm);
$wow->getGuildNews('$guildName', $realm);
$wow->getGuildChallenge('$guildName', $realm);
$wow->getLeaderboard2v2();
$wow->getLeaderboard3v3();
$wow->getLeaderboard5v5();
$wow->getLeaderboardRbg();
$wow->getQuest(13146);
$wow->getRealmStatus();
$wow->getRecipe(33994);
$wow->getSpell(8056);
$wow->getDataResourceBattlegroups();
$wow->getDataResourceCharacterRaces();
$wow->getDataResourceCharacterClasses();
$wow->getDataResourceCharacterAchievements();
$wow->getDataResourceGuildRewards();
$wow->getDataResourceGuildPerks();
$wow->getDataResourceGuildAchievements();
$wow->getDataResourceItemClasses();
$wow->getDataResourceTalents();
$wow->getDataResourcePetTypes();
</code></pre>

### Authentification

If you want to use the authentification feature of this package you have only to inject a jpWoWAuthentification object with the private key. The private function from jpWoW::_performRequest() does than the setup for every call for you.

<pre><code class="php">
$region = new jpWoWRegion('europe', 'de_DE');
$auth = new jpWoWAuthentication();
$auth->setPrivateKey('MyPrivateKey');
$wow = new jpWoW($region, $auth);
</code></pre>

For more details see: [blizzard.github.io/api-wow-docs/#features/authentication](http://blizzard.github.io/api-wow-docs/#features/authentication)