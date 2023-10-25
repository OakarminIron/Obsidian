`@web/core/action_swiper/action_swiper`

This is a component that can perform actions when an element is swiped horizontally. The swiper is wrapping a target element to add actions to it. The action is executed once the user has released the swiper passed a portion of its width.

| Name               | Type    | Description                                                                     |
|--------------------|---------|---------------------------------------------------------------------------------|
| animationOnMove    | Boolean | optional boolean to determine if a translate effect is present during the swipe |
| animationType      | String  | optional animation that is used after the swipe ends (bounce or forwards)       |
| onLeftSwipe        | Object  | if present, the actionswiper can be swiped to the left                          |
| onRightSwipe       | Object  | if present, the actionswiper can be swiped to the right                         |
| swipeDistanceRatio | Number  | optional minimum width ratio that must be swiped to perform the action          |
