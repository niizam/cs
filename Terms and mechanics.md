Terms and mechanics
This guide will help you understand the common terms and mechanics in Counter Side.

Last updated: 12/03/2024
Foreword

This guide is made for two reasons: first, to explain the common terms used in the community, and second, to explain vague and/or intricate ingame mechanics.

Disclaimer: this guide contains mechanics not confirmed by the developers, but proven experimentally by players
Terms

MDL - Max Damage Limit. Any incoming damage exceeding this percent of the unit’s max hp is reduced by 96%. Ingame it is listed as “Damage Taken Limit”.

Iframe - Invincibility frames. Some units cannot be damaged during certain animations, most often ultimate skills.

EE - Exclusive Equipment, or the unique gear that only one unit can equip. For example, Kim Sobin's EE is the Fairy’s Infinite Ammo accessory.

CDR - Cooldown reduction, same thing as Skill Haste.

RTA - Ranked Gauntlet, or PVP.

DC - Danger Close, a bi-weekly PVE game mode where you fight a boss against other players to compete for the leaderboards.

SP/SH - Shadow Palace, a PVE game mode for resources primarily to create Spectral gear.
Mechanics
Hit and Eva interactions

    If an attacker's Hit is greater than or equal to 1.875x an enemy's Eva value, the enemy will not be able to evade any incoming attacks. Notably, this may be interpreted as the attacker's Hit% > opponent's Eva%. This is often referred to as the 1.875x rule,
    If your Hit is less than 1.875x an enemy's Eva, the enemy has a chance to evade based on their Eva value, which you can see by clicking on the Eva stat in a unit's stats screen. This value is determined as Eva% = EVA / EVA+800,
    The damage dealt on a miss due to successful enemy evasion is determined by the hit stat, being equal to 10% + (90% x hit%). Hit% can be found on the stats screen, and is calculated as Hit% = Hit / Hit+1500,
    When an attack is evaded, any hitstun and critical hits will be nullified, unless the unit has sure crit, where the attack will still miss but be able to crit.

Perfect Evasion, Sure Fire, and Blind

    Perfect Evasion is a buff which certain units have that allows them to evade any incoming attacks, no matter their actual Eva vs the enemy's Hit. Even if the enemy's Hit is 1.875x their own Eva or more, they will still evade the attack. This makes Perfect Evasion a very good mechanic for survival, due to it greatly reducing incoming damage. Perfect Evasion also allows a unit to ignore hitstuns, but stuns will still work on them.
    Blind is a debuff that makes the opponent always miss, regardless of your unit’s Eva stat.
    Sure Fire is a buff that makes the unit always hit, regardless of the opponent’s evasion.
    Unavoidable is a debuff that makes the opponent unable to evade regardless of the attacker's Hit and the opponent's Eva.
    When any combination of guarantee hit and guarantee miss is combined, the interaction reverts to the normal 1.875x rule. This is true no matter how many are in effect.

Skill Haste (CDR)

    The formula for cooldown after skill haste is applied is new CD = base CD / 1 + Skill Haste,
    Effects that give a flat cooldown reduction effect (e.g. Gaeun passive -2s on ult cd) are calculated using the base cooldown.

CRIT stat

    Crit rate is calculated as Crit stat x 0.5%. It also caps at 85%.
    Crit and Spectral Chain gear sets are multiplicative to the base crit. For example, a unit with 1000 (50%) crit using two sets of Spectral Chain gets 1000(100%+20%) = 1200 (60%) crit.

Barriers

    Barriers prevent damage from overflowing into HP: that is, if a unit takes a single hit of damage higher than the barrier value, the barrier will be removed but the HP will be untouched.
    Multiple layers of barriers will prevent damage from overflowing to successive layers.
    Barriers are counted as buffs and are thus removed by buff removal, unless it is an uncancellable barrier. If a barrier is lost through any means, then any effects tied to the barrier are also lost.
    MDL applies to barriers as it would to normal HP.
    Except for uncancellable barriers, applying a barrier to a sleeping unit will wake them up. This is a side effect of how they are applied, and is not a hard rule.

Heal Block

    Heal block is capped to 100%, at which point no healing takes place.

Role Advantage and Disadvantage, and Anti-Type Dmg Res

    Role Advantage Damage is base +30%, and disadvantage is at -30%.
    Similarly, Role Advantage Res is +30%, and disadvantage is -30%.
    Role Advantage/Disadvantage Damage/Res buffs are multiplicative to the 30% base, meaning a 50% role adv dmg buff is only +15% dmg.
    Role Advantage/Disadvantage Damage/Res belong to Category 3. This means they are multiplicative to everything else.
    Role disadvantage res buffs are only effective if the attacker has role advantage, and has role advantage damage buffs.

Melee and ranged distance

    Melee distance is 500 game units or 5m. This is inferred from a patch note here,
    Whether the damage is regarded as melee or ranged damage is determined from the center of the character models. This means some especially wide enemies such as the moderators take ranged damage from units that would normally do melee damage.
    Ingame, melee range is about equal to the range of Irie Alford’s aura.
    Since melee/ranged damage is determined purely via distance, units are not strictly locked into one form of damage. A Ranger that usually deals ranged damage can also deal melee damage if an enemy unit gets too close to them.

Origin

Origin is a PVE system in which certain units will get a set percentage damage and dmg res buff if their origin matches the opponent's.

The buff numbers are as follows:
Unit Rarity Dmg buff	Dmg res
Awakened SSR    40%	30%
SSR	30%	20%
SR	10%	10%
Summon	20%	20%

Note that all summons have the same Origin buffs regardless of the summoner's rarity.
Defense and Damage res interactions

The formula for Defense damage reduction is DEF% = DEF/(DEF + 1000) * 100%.

    DEF Reduction and DEF Penetration apply to the flat defense stat.
    When both DEF Reduction and Penetration are used on the same target, they are applied multiplicatively.

The formula for final damage done looks like this:
Damage multiplier = [ (1 - DEF%) * (1 + Cat 1 dmg - Cat 1 res) ] * [ 1 + Cat 2 dmg - Cat 2 res ] * [ 1 + 0.3 * Role Damage ] * [ 1 + Cat 4 dmg - Cat 4 res ] * Dodge * EventDef * Extra stats * MDL

    [ (1 - DEF%) * (1 + sum of 1st Category stats) ] is lower bound at 20%.
    [ 1 + sum of 2nd Category stats ] is lower bound at 50%.
    Role Damage is -1 when attacking at disadvantage, and ( 1 + Cat 3 dmg - Cat 3 res) is lower bound at 100% when attacking at advantage.
    Cat 4 stats are also known as Origin, which is PVE exclusive.
    True Damage: Def% = 0. In addition, [ (1 - DEF%) * (1 + Cat 1 dmg - Cat 1 res) ] is lower bound at 100%.
    Dodge: See the Hit and Eva interactions section.
    EventDef: Completely independent dmg reduction used by certain PVE enemies like Tyrant Armor during its hit check.
    Extra stats = Special stats used only in PVE, referred to ingame as "Combat Environment", for example DMG Reduction when there is a barrier, and for ban penalties in PVP. Lower bound at 1%.
    MDL: See MDL in the Terms section.

Category 1 stats (capped at 80% reduction):

    Anti-Counter/Soldier/Mech DMG and DMG Res
    Anti-CO DMG and DMG Res
    Anti-Striker/Sniper/Defender/Supporter/Tower/Siege DMG and DMG Res
    Anti-Ground/Air DMG and DMG Res
    Anti-Ranged/Melee DMG and DMG Res
    DMG Tolerance
    DMG Increase Suppression
    DMG Increase Defense
    DMG RES Penetration
    DMG RES Suppression

Category 2 stats (capped at 50% reduction):

    DMG Taken RDC
    AOE DMG Res
    DMG increase and decrease
    Skill DMG and DMG Res
    Ultimate DMG and DMG Res

Category 3 stats:

    Role Advantage/Disadvantage

Category 4 stats:

    Origin type bonuses

Generally, "res" stats are category 1 and "rdc" stats are category 2.
DMG TLRNC

    Also known as damage tolerance, increases Dmg Res to the attacker by the amount given (2% for all currently known cases) every time the unit is hit, to a max of 80%.
    Tolerance is counted separately for each attacker - an Ifrit and a Xiao Lin attacking the same Esterosa will have different counts on Esterosa for her damage tolerance.
    Tolerance is reset upon redeploying the unit.
    Tolerance is additive to anti-type damage res for damage calculations.

Protect

    For every Defender an AOE attack hits, the subsequent units to be hit will gain 7% damage res to the attack.
    Protect dmg res is multiplicative with anti-type damage res for damage calculations.

Crit DMG Res

    Crit DMG Res, or simply CDMG Res, subtracts the amount of CDMG Res from the opponent's CDMG stat. This means 35% CDMG Res vs an opponent with 50% CDMG will make their effective CDMG only 50% - 35% = 15%.
    Going above the opponent’s CDMG with CDMG Res will simply set their CDMG to 0%. Crits will still display on screen, but not do extra damage.
    CDMG Res is independent of the DEF and Dmg Res limit.
    Most PVE enemies only have 50% CDMG; This is related to proper tank set tuning for endgame PVE, where at least 50% CDMG Res is used to completely negate CDMG from PVE enemies.

Valid Hit

    Attacks with a valid hit of 1 can only hit one unit.
    Attacks with more than 1 valid hit can hit all units in range, unless the attack specifies that it only hits up to its valid hit. After hitting a number of units equal to the attack’s valid hit, each additional unit only takes 30% of the attack’s damage and cannot be critically hit.

AOE Res

    AOE Res reduces damage from attacks that are capable of hitting more than 1 enemy. This is taken from one of the KR patchnotes.
    After the damage formula rework, AOE Res belongs to the Category 2 of stats.

Hitstun, stun, hitstun immunity interactions

    Knockback, levitate, and pull are all regarded as hitstuns and can be prevented through “super armor” or evasion
    Every hitstun has their own power tier - determining which super armor they can bypass.
    Most passive, special skills will have “special” tier hitstun, and ultimates will have “ultimate'' tier hitstun - with few exceptions being Rosaria’s special having ultimate hitstun at level 5. (Despite what this sounds like, Shiyoon can still counter Rosaria's special even though it is stated ingame that he can only counter special skill tier or lower hitstuns).
    “Immunity to special hitstun or lower” will mean that you are immune to special skills’ hitstuns but not ultimates.
    There is a hitstun tier above ultimate, but it is very rare and the only currently known sources are Matador ship second skill’s pull and Nervier DC boss knockback. The only playable units with immunity to this tier of hitstun are Evolved One (Permanent), Awakened Hilde (Special), Horizon (During passive), and Dracasia (During ultimate).
    Stuns will always ignore evasion (including Perfect Evasion) or hitstun immunity, but can be prevented with “Stun immunity”.
    Most of the stuns will NOT stun mechas unless explicitly stated (e.g. Kestrel skill).

Counter attack

    Normal counter attacks can be triggered by attacks that have a hitstun power tier lower than special. Currently, this means normal tier only. These are usually found on counter stances.
    Special counter attacks can be triggered by attacks that have a hitstun power tier of special or lower, and have a hitstun duration. Attacks that do not have a hitstun duration will not trigger special counters. These counters are always special skills.
    Ultimate counter attacks does not currently exist.
    If a unit has more than one counter attack (currently only Awakened Shiyoon), then jank ensues. The counter does not distinguish between sources of triggers. If any of the triggers for a counter attack pop, then the unit will use their counter attacks once per trigger in this order: stance (normal), special, ultimate.
        This means it is possible for Awakened Shiyoon to counter a special skill with his normal counter. 
    A successful counter will forcibly stagger the attacker. This works on bosses for cancelling/breaking patterns.

Debuff Res

CC Res was renamed to Debuff Res.

    Debuff Res decreases both the duration and value of incoming debuffs. The value of the reduction is directly taken from the Debuff Res %. For example, 10% Debuff Res means the value and duration of incoming debuffs is reduced by 10%, and 50% Debuff Res means they are instead reduced by 50%.
    Debuff Res applies to anything that is a debuff. Aura debuffs are complicated, and are best treated case by case.
    Debuff Res has an 80% cap. 

Execute

    A successful execute replaces the standard damage calculation with twice the target’s remaining HP as damage.
    Only counter attack's 90% damage reduction and state based damage reduction interacts with it.

Stealth

    Stealth makes units untargetable. They may still be hit by collateral from AOE attacks, however.

Buff/Debuff Removal and Blocking

    Buff blocking prevents any non-permanent or uncancellable buffs from applying. Buff removal also cannot remove the said buffs. The same goes for debuff blocking.
    Not all buffs with infinite durations are considered permanent: for example, Eddie Fisher’s aura can be removed or blocked and will NOT return until redeployed.
    There is no pattern to which infinite buffs are permanent or not.