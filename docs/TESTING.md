# Testing Checklist

## Connection

- [ ] Connect
- [ ] Disconnect
- [ ] Connect again

## Basic control

- [ ] ON
- [ ] OFF
- [ ] RGB
- [ ] Brightness

## Effects

- [ ] Preset effects
- [ ] Color Flow start
- [ ] Color Flow stop
- [ ] Custom Color Flow

## Personalization

- [ ] Favorites create
- [ ] Favorites update
- [ ] Favorites delete
- [ ] Scenes create
- [ ] Scenes update
- [ ] Scenes delete

## Automation

- [ ] Timer / Auto OFF
- [ ] Schedule

## Other

- [ ] Energy estimate
- [ ] Music Reactive
- [ ] Backup export
- [ ] Backup import
- [ ] Developer / diagnostic view

## Regression rule

If a new feature breaks an already verified BLE function, revert the feature change before continuing.

The BLE protocol should not be changed just to improve UI behavior.
