# Labymod API Docs
shouts out neliz

> [!NOTE]
> This is unofficial Documentation for the LabyMod API and I am in no way associated with LabyMedia, some endpoints may be missing or incorrect.

## Player UUID to LabyMod profile 
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `/userdata/:dashed_uuid.json`

**Description:** This returns LabyMod user data such as cosmetics, groups, and user role.

**Request:**
```http
GET /userdata/34e57efa-5783-46c7-a9fc-890296aaba1f.json
```

**Response:**
```json
{
  "c": [ // Cosmetics
    {
      "i": 8, // Cosmetic ID
      "d": [ // Cosmetic Data
        "0a53e04c-5ed0-46e3-a522-7043aaa604a7",
        ...
      ]
    },
    ...
  ],
  "e": [ // Emote IDs
    4,
    ...
  ],
  "f": { // Flatrate
    "e": true
  },
  "st": { // No clue
    "p": [
      1,
      4,
      20,
      6,
      2,
      11,
      5
    ]
  },
  "r": { // Role
    "i": 25, // Role ID
    "v": false
  },
  "g": [ // Groups
    {
      "i": 13 // Group ID
    }
  ]
}
```

## List of LabyMod Cosmetics
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /cosmetics/index.json`

**Description:** This returns a list of every LabyMod Cosmetic.

**Request:**
```http
GET /cosmetics/index.json
```

**Response:**
```json
{
  "cosmetics": { // The Object key, Cosmetic ID and Texture Directory are the same.
    "0": {
      "id": "0",
      "type": "COSMETIC", // COSMETIC | FLYING_PET | SHOULDER_PET | WALKING_PET
      "name": "Cloak",
      "options": [
        "is_custom",
        ...
      ], // is_custom | texture | rgb | offset | side | shoulder_side | mojang_uuid
      "scale": "1",
      "attached_to": "BODY", // BODY | HEAD | LEG | ARM
      "texture_type": "USER_BOUND", // USER_BOUND | TYPE_BOUND | MOJANG_BOUND
      "hide_cape": true,
      "texture_directory": "0",
      "draft": false,
      "nametag_offset": 0,
      "default_data": [
        "1"
      ],
      "category": "CLOAK", // CLOAK | BACK | WING | FACE | HAT | BODY | HEADGEAR | SHOES | PARTNER | ARMS | PETS | AURA | LANYARD | UNDERGLOW
      "position": "BACK", // BACK | LEGS_BACK | FACE | HEAD_TOP | FEET | HIPS | ARM | CHEST | SHOULDER
      "option_list": [
        "is_custom",
        ...
      ], // is_custom | texture | rgb | offset | side | shoulder_side | mojang_uuid (OPTIONAL)
      "frame_aspect_ratio": {
        "width": 1,
        "height": 1
      }, // (OPTIONAL)
      "mirror_type": "DUPLICATE", // DUPLICATE | ROTATE (OPTIONAL)
      "mirror": true, // (OPTIONAL)
      "move_type": "BOTH", // BOTH | IDLE_ONLY | MOVE_ONLY (OPTIONAL)
      "frame_animation_delay": 500 // (OPTIONAL)
    },
    ...
  }
}
```

## Get Cosmetic Animations
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /cosmetics/:cosmetic_id/animation.json`

**Description:** This returns the animations for a cosmetic.

## Get Cosmetic Geometry
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /cosmetics/:cosmetic_id/geo.json`

**Description:** This returns the geomoetry for a cosmetic.

## List of LabyMod Emotes
**Subdomain:** `https://neo.labymod.net/`
**Endpoint:** `GET /cosmetics/index.json`

**Description:** This returns a list of every LabyMod Cosmetic.

**Request:**
```http
GET /cosmetics/index.json
```

**Response:**
```json
{
  "emotes": {
    "5": {
      "id": 5,
      "name": "Bow thanks",
      "attachedTo": "NONE", // NONE | ARM
      "ignoredAbortActions": [
        "MOVEMENT",
        ...
      ], // MOVEMENT | JUMPING | SPRINTING | SNEAKING | FLYING | SWIMMING | DAMAGE | ATTACKING (OPTIONAL)
      "draft": true, // Won't show up if false (OPTIONAL)
      "abortActions": [
        "MOVEMENT",
        ...
      ], // MOVEMENT | JUMPING | SPRINTING | SNEAKING | FLYING | SWIMMING | DAMAGE | ATTACKING (OPTIONAL)
      "props": true, // Won't show up if false (OPTIONAL)
      "disabledSuspensions": [
        "POSITION",
        ...
      ], // POSITION | ROTATION | SCALE (OPTIONAL)
      "textureRatio": {
        "width": 1,
        "height": 1
      }, // (OPTIONAL)
      "textureAnimationDelay": "100" // (OPTIONAL)
    },
    ...
  }
}
```

## Get Emote Animations
**Subdomain:** `https://neo.labymod.net/`
**Endpoint:** `GET /emotes/:emote_id/animation.json`

**Description:** This returns the animations for a emote.

## List of LabyMod Sticker Packs
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /stickers.json`

**Description:** This returns a list of every LabyMod Sticker pack.

**Request:**
```http
GET /stickers.json
```

**Response:**
```json
{
  "packs": [
    {
      "id": 1,
      "name": "Halloween-Pack",
      "stickers": [
        {
          "id": 1,
          "name": "Pumpkin",
          "tags": [
            "halloween",
            "kürbis",
            "pumpkin"
          ]
        },
        ...
      ]
    },
    ...
  ]
}
```

## List of LabyMod Addons & Categories
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /addons.json`

**Description:** This returns a list of every LabyMod Addon and a list of possible categories.

## Get List of LabyMod Groups
**Subdomain:** `https://dl.labymod.net/`
**Endpoint:** `GET /groups.json`

**Description:** This returns a list of every LabyMod group.

**Request:**
```http
GET /groups.json
```

**Response:**
```json
{
  "groups": [
    {
      "id": 1,
      "name": "administrator",
      "nice_name": "Administrator",
      "color_hex": "e84c3c",
      "color_minecraft": "4",
      "tag_name": "ADMIN",
      "display_type": "ABOVE_HEAD",
      "is_staff": true
    },
    ...
  ]
}
```
