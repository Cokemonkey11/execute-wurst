# Demo

[<img src="demo_thumbnail.jpg" />](https://i.imgur.com/QVEGmBo.mp4)

# Test repo

[link](https://github.com/Cokemonkey11/WurstExecuteTest)

# Example code:

```
constant seq = new LinkedList<ExecuteExecutable>()
    ..add(new ExecuteLockTarget())
    ..add(new ExecuteLockCaster())
    ..add(new ExecuteAnimate(UnitAnimations.HeroBloodElf.spellChannel.idx))
    ..add(new ExecuteLightning(3.5, "AFOD"))
    ..add(new ExecuteFxTarget(Abilities.soulBurnbuff))
    ..add(new ExecuteWait(.5))
    ..add(new ExecuteFxCaster(Abilities.obsidianRegenAura))
    ..add(new ExecuteKnockup(1500.))
    ..add(new ExecuteWait(.65))
    ..add(new ExecuteForgetTargetVelocity())
    ..add(new ExecuteWait(.1))
    ..add(new ExecuteFxTarget(Abilities.darkPortalTarget))
    ..add(new ExecuteKnockArcToCaster(1400.))
    ..add(new ExecuteAnimate(UnitAnimations.HeroBloodElf.spell.idx))
    ..add(new ExecuteWait(.1))
    ..add(new ExecuteUnlockCaster())
    ..add(new ExecuteFxTarget(Abilities.bloodImpact))
    ..add(new ExecuteWait(1.))
    ..add(new ExecuteFxTarget(Abilities.bloodImpact))
    ..add(new ExecuteWait(1.))
    ..add(new ExecuteFxTarget(Abilities.bloodImpact))

init
    EventListener.add(EVENT_PLAYER_UNIT_SPELL_EFFECT) ->
        let target = EventData.getSpellTargetUnit()
        EventData.getTriggerUnit().issueImmediateOrder("stop")

        if EventData.getSpellAbilityId() == 'AHbn' or EventData.getSpellAbilityId() == 'AHhx'
            new Execute(
                EventData.getTriggerUnit(),
                target,
                seq
            )
```
