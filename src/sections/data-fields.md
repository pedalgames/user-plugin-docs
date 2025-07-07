# Data fields

These are existing data fields which can be referenced in ```display``` HTML fragment with the data-field attribute:

```html
<div>
    <div><span data-field="hr"></span><div>
</div>
```

The recommended way to include a data field is to use the data-field attribute as shown above.

There are also corresponding CSS variables so the field ```something``` has a direct corresponding variable ```--something``` unless noted. Variables all has a ```--something-previous``` to reference the prior second.

Alternatively (DEPRECATED), data can be included in the display using CSS classes. All elements with one of the classes documented below will have it's innerText replaced with the corresponding data at run-time. 

That means that

```html
<div>
    <div><span data-field="hr"></span><div>
</div>
```

is equivalent to
```html
<div>
    <div><span class="data-field-hr"></span><div>
</div>
```



## Average for the session

These fields are based on the average of all received data during a session

- average-power
- average-heartrate
- average-hr

 
## Average, calculated per user preference

- player-power-average
- player-cadence-average
- player-zone-average
- player-wkg-average
- player-pct-ftp-average

There are some special fields for HR which is not actually averaged per a user preference but maybe will be in the future. For now they are just implemented based on 'instant' hr to mirror the way we have fields for power.

- player-hr-average
- player-hr-zone-average
- player-pct-hr-max-average
 
## User preferences

There are the following classes you can use in game definitions to include the data set in the Player tab

- player-name
- player-weight
- player-ftp
- player-hr-max
- player-power-average-over
- player-cadence-average-over

## Player score

- player-level
- player-xp
- player-session-xp

## Instant (player/ride data)

- power-instant
- cadence-instant
- hr
- heartrate
- calories
- work
- wkg
- pct-ftp
- zone
- pct-hr-max
- hr-zone
- tss
- np
- if
- ef
- vi
- speed-kph
- speed-kmh
- speed-mph
- distance-km
- distance-mi
- climbing
- climbing-unit
- climbing-m
- climbing-f
- real-altitude
- real-altitude-unit
- real-altitude-m
- real-altitude-f
- gradient
- lap
- time-in-game  
  (in seconds)
- seconds-in-ride
- time-in-ride
- time-in-ride-seconds  
  (CSS class: "data-time-in-ride time-minutes-seconds")
- time-in-ride-minutes  
  (CSS class: "data-time-in-ride time-minutes-seconds")
- time-in-ride-minutes-seconds
  (CSS class: "data-time-in-ride time-minutes-seconds")
- seconds-in-ride-seconds
  (CSS class: "data-seconds-in-ride time-seconds")
- seconds-in-ride-minutes
  (CSS class: "data-seconds-in-ride time-minutes")
- seconds-in-ride-minutes-seconds  
  (CSS class: "data-seconds-in-ride time-minutes-seconds")

### Draft (mostly Zwift specific)

- draft
- max-draft

### Zwift fields

- rideons
- player-zwift-world
- player-zwift-route
- player-zwift-road
- player-zwift-road-elapsed-time
- player-zwift-road-distance
- player-zwift-road-climbing
- player-zwift-is-portal
- player-zwift-slope-scale
- player-x
- player-y
- player-z

## Instant (other)

- time-of-day-hms-localized  
  Time of day, localized format, hours+minutes+seconds  
  (CSS class: "data-time-of-day time-hms-localized")
- time-of-day-hm-localized  
  Time of day, localized format, hours+minutes  
  (CSS class: "data-time-of-day time-hm-localized")
- time-of-day-hms  
  Time of day, 24 hour format, hours+minutes+seconds  
  (CSS class: "data-time-of-day time-hms")
- time-of-day-hm  
  Time of day, 24 hour format, hours+minutes  
  (CSS class: "data-time-of-day time-hm-localized")



## Game fields

Calculated from game/plugin timer start

- game-calories
- game-distance-m
- game-distance
- game-distance-unit
- game-distance-km
- game-distance-m
- game-climbing
- game-climbing-unit
- game-climbing-m
- game-climbing-f

### Timers

- seconds-in-game
- timer-started
- timer-finished
- timer-seconds
- first-second
- this-second

