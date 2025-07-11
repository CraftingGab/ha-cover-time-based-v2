# Cover time based integration by [@CraftingGab](https://www.github.com/CraftingGab)
A Home Assistant integration to control your cover based on time.

This integration is based on [davidramosweb/home-assistant-custom-components-cover-time-based](https://github.com/davidramosweb/home-assistant-custom-components-cover-time-based/).
And based on  [Sese-Schneider/ha-cover-time-based](https://github.com/Sese-Schneider/ha-cover-time-based)

It improves the original integration by adding tilt control and virtual Buttonpress.

**Features:**

- Control the height of your cover based on time.
- Control the tilt of your cover based on time.

*To enable tilt control you need to add the `tilting_time_down` and `tilting_time_up` options to your configuration.yaml.*

## Install

### HACS

*This repo is available for install through the HACS.*



## Setup

### Example configuration.yaml entry

```
cover:
  - platform: cover_time_based
	devices:
	  room_rolling_shutter:
	   name: Room Rolling Shutter
	   open_switch_entity_id: switch.wall_switch_right
	   close_switch_entity_id: switch.wall_switch_left
	   travelling_time_down: 23
	   travelling_time_up: 25
	   tilting_time_down: 2.3
	   tilting_time_up: 2.7
```

### Options

| Name                   | Type         | Requirement                                     | Description                                                 | Default |
|------------------------| ------------ |-------------------------------------------------|-------------------------------------------------------------|---------|
| name                   | string       | **Required**                                    | Name of the created entity                                  |         |
| open_switch_entity_id  | state entity | **Required** or `cover_entity_id`               | Entity ID of the switch for opening the cover               |         |
| close_switch_entity_id | state entity | **Required** or `cover_entity_id`               | Entity ID of the switch for closing the cover               |         |
| stop_switch_entity_id  | state entity | *Optional* or `cover_entity_id`                 | Entity ID of the switch for stopping the cover              | None    |
| cover_entity_id        | state entity | **Required** or `open_\|close_switch_entity_id` | Entity ID of a existing cover entity                        |         |
| travelling_time_down   | int          | *Optional*                                      | Time it takes in seconds to close the cover                 | 30      |
| travelling_time_up     | int          | *Optional*                                      | Time it takes in seconds to open the cover                  | 30      |
| tilting_time_down      | float        | *Optional*                                      | Time it takes in seconds to tilt the cover all the way down | None    |
| tilting_time_up        | float        | *Optional*                                      | Time it takes in seconds to tilt the cover all the way up   | None    |
| is_button              | boolean      | *Optional* (`cover_entity_id` not supported)    | Treats the switches as buttons, only pressing them for 1s   | False   |
| is_button_time         | int          | *Optional*					  | Delay from virtual Button press 				| 1	  |


[license-shield]: https://img.shields.io/github/license/Sese-Schneider/ha-cover-time-based.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/maintenance/yes/2025.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/Sese-Schneider/ha-cover-time-based.svg?style=for-the-badge
[releases]: https://github.com/Sese-Schneider/ha-cover-time-based/releases
