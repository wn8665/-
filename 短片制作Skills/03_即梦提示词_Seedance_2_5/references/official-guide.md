# Seedance 2.5 Official Guide Reference

This file condenses the official Jimeng/Dreamina Seedance 2.5 manual for prompt-writing use. It was checked against the public guide on 2026-07-31:

- [Official Seedance 2.5 manual](https://bytedance.larkoffice.com/wiki/RXh5ww6EqighMdkVTMccm2d4n7e)
- [Jimeng / Dreamina](https://jimeng.jianying.com/)

Platform UI and limits can change. If the user needs current billing, availability, or an exact production limit, verify the live product.

## Contents

1. [What changed in 2.5](#what-changed-in-25)
2. [Input and output limits](#input-and-output-limits)
3. [Material preparation guidance](#material-preparation-guidance)
4. [Modes and duration behavior](#modes-and-duration-behavior)
5. [Official prompt formulas](#official-prompt-formulas)
6. [Timestamp and reference rules](#timestamp-and-reference-rules)
7. [Editing and control capabilities](#editing-and-control-capabilities)
8. [Reliability notes](#reliability-notes)

## What changed in 2.5

Seedance 2.5 expands Seedance 2.0’s image, video, audio, and text workflow with:

- Native generation up to 30 seconds.
- A separate ultra-long mode for 30–180 seconds.
- Video extension that can produce a final result up to 60 seconds.
- Second-level timestamp control.
- More reference images, videos, and audio.
- Audio-only multimodal input.
- Improved realistic texture, complex motion, cut consistency, and multilingual understanding.
- More precise multi-person identity and voice reference.
- Smart/advanced video editing, local removal and replacement, and viewpoint changes.
- BGM separation/removal while retaining speech.
- Creative transfer, green-screen output, white-model spatial control, seamless transitions, and multi-panel storyboard reference.

The manual says Chinese, English, Spanish, Indonesian, and Malay receive focused support and also lists Thai, Arabic, Portuguese, Vietnamese, Japanese, and Korean.

## Input and output limits

### Images

- Up to 30 reference images per request.
- Recommended source dimensions stay within 300–6000 px per side.
- Documented aspect ratio range: greater than 0.4 and less than 2.5.
- Documented single-image size: below 30 MB.
- Accepted formats listed by the guide: JPEG, PNG, WebP, BMP, TIFF, GIF, HEIC, and HEIF.

### Video

- MP4 and MOV.
- A single reference video: 2–30 seconds; practical accepted range documented as 1.8–30.2 seconds.
- Up to 10 reference videos.
- Combined reference-video duration: no more than 30 seconds; practical boundary documented as 30.2 seconds.
- Documented source resolution: 480p–4K.
- Documented frame-rate range: 24–60 fps.
- Documented single-video size: no more than 200 MB.

### Audio

- WAV and MP3.
- A single reference audio clip: 2–30 seconds; practical accepted range documented as 1.8–30.2 seconds.
- Up to 10 reference audio clips.
- Combined reference-audio duration: no more than 30 seconds; practical boundary documented as 30.2 seconds.
- Documented single-audio size: no more than 15 MB.
- Audio-only reference generation is supported in 2.5.

### Generation

- Standard duration parameter: automatic or 4–30 seconds.
- Standard output resolution choices documented by the guide: 480p and 720p.
- Ultra-long mode: 30–180 seconds.

Do not substitute third-party claims such as native 4K output for the official 480p/720p settings unless the live Jimeng interface confirms a newer option.

## Material preparation guidance

The official manual gives practical “best range” recommendations in addition to hard limits:

| Use case | Best range | Stretch range / trade-off |
| --- | --- | --- |
| Subject video/audio references | 1–5 subjects, 5–10 seconds | 6–10 subjects or longer clips may be less stable |
| Subject image references | 1–8 subjects | 9–12 subjects may require retries |
| More than five image subjects | Prefer separate single-view images | One collage containing many views is less stable |
| Video to edit | Within 20 seconds | Longer sources may be less stable |
| Reference images for a video edit | 1–5 images | 6–8 images may be less stable |

For multi-angle identity references, prefer several clean images, one view per image, instead of a single crowded contact sheet.

## Modes and duration behavior

### 全能参考

Use for text-only or multimodal generation, creative transfer, audio reference, storyboard reference, white-model input, green-screen tasks, and most 4–30 second generation.

### 首尾帧

Use when opening and ending composition matter. Treat the frames as boundary conditions, then describe the motion and visual logic that connect them.

### 超长视频

- Generate 30–180 seconds in one operation.
- Write a full script or prompt, choose ultra-long mode, then choose duration.
- Structure the prompt in scene blocks. Maintain global character and production rules across all blocks.

### 视频延长

- The source video must be no longer than 30 seconds.
- Extend by 4–30 seconds per operation.
- The prompt applies to the newly generated extension, while the original segment is retained.
- Repeated extension is possible while the newest source remains within 30 seconds.
- A 30-second source can be extended by 30 seconds for a 60-second final video.

### 智能编辑

Upload a source video and describe the desired change in text. Use when the target can be identified without drawing on a frame.

### 高级编辑 / 视频编辑

Use boxes, arrows, markers, or frame annotations to identify the exact object and timestamp. Pair the annotation with a precise text instruction and a preserve list.

## Official prompt formulas

These formulas are condensed from the manual. Use them as information order, not as rigid punctuation.

### Basic prompt

```text
素材描述 + 一句话概述 + 具体情节描述 + 全局补充
```

- Material description: asset number plus exact purpose.
- One-sentence overview: subject, location, event, genre/style, and notable camera behavior.
- Plot: chronological story or timestamped actions.
- Global supplement: elements that must hold throughout.

### Realistic person

```text
年龄/人种
+ 肤色与皮肤质感
+ 面部细节
+ 眼神
+ 发型发色
+ 服装与材质
+ 体型、情绪与气质
+ 其他要求
```

Use observable traits. Avoid only saying “漂亮”, “高级”, or “有电影感”. Describe bone structure, skin texture, eyes, hair, garment construction, posture, and emotional presence.

### Native 30-second video

```text
总述名称 + 多模态参考层 + 全局设定 + 时间戳剧本分镜
```

- Start with a short title or production premise.
- Bind each reference to identity, scene, motion, voice, or style.
- Declare environment, visual treatment, and camera grammar globally.
- Use four to six timestamped beats for the story.

### Ultra-long video

```text
全局参数 + 素材描述 + 一句话概述 + 具体情节/故事线 + 全局补充
```

State total duration and aspect ratio. Divide the storyline into scenes with explicit transitions. Keep character identity, wardrobe, production style, time of day, and sound logic global unless the story intentionally changes them.

### Video extension

The official guide highlights direction words such as `向前延长`, `向后延长`, `延续`, and `续写`. Choose the one that matches the task.

Recommended operational formula:

```text
向前/向后延长 X 秒
+ 源视频边界状态
+ 新增时间段内容
+ 需要延续的动作、人物、场景、光影、镜头与声音
```

The extension timeline starts at 0 for the new segment unless the live UI expects absolute time.

### Smart and advanced edit

```text
具体修改对象 + 动作/变化 + 生效时序 + 保持不变项
```

Example structure:

```text
在 00:01–00:08，将框选人物的蓝色牛仔裤改为深黑色西装裤。
全片保持新裤子一致；人物脸部、发型、动作、镜头、背景和光影不变。
```

### White-model control

```text
参考声明 + 对应关系映射 + 时间线剧情/动作 + 场景处理 + 整体收束
```

- Reference declaration: specify that the source provides camera, action, blocking, scale, or motion path.
- Mapping: map every proxy character/object to a final reference.
- Timeline: retain the proxy timing and physical trajectory.
- Scene treatment: replace or render the environment using text or an image reference.
- Overall close: preserve composition, camera continuity, and spatial relationships.

## Timestamp and reference rules

### Timestamps

- Use explicit ranges such as `0–5秒`, `5–11秒`, and `11–15秒`.
- Cover the full duration once.
- Keep global style outside the timestamp blocks.
- Put camera movement and sound cues in the interval where they occur.
- Use fewer, larger blocks for 60–180 second videos.

### References

Use:

- `@图片1`
- `@视频1`
- `@音频1`

Always add the role:

- `@图片1作为角色外形与服装参考`
- `参考@视频1的运镜和动作节奏`
- `@图片2作为场景与光影参考`
- `参考@音频1的音色、语速与情绪`

Do not use an unnumbered phrase like `参考图片` when several assets exist.

## Editing and control capabilities

### BGM separation/removal

Ask to remove only the music bed and retain speech, environmental sound, and any required existing visual elements. Specify whether the result should be silent outside speech.

### Creative transfer

Describe what to transfer: motion, emotional tone, camera grammar, transition idea, edit rhythm, or a deeper creative structure. Avoid “完全复制所有内容”; list the transferable dimensions and the new subject mapping.

### Local removal and replacement

Identify the object, time range, and spatial location. State how the removed region should be filled and which surrounding elements must remain.

### Viewpoint modification

Describe both the target viewpoint and the camera path, for example high aerial push-in, low-angle orbit, or first-person travel. Preserve subject scale and scene geometry unless the change intentionally reframes them.

### Voice reference

Use clean speech without background noise when possible. State the exact line, speaker, emotion, pace, and that the voice should reference `@音频N`.

### Multi-person reference

Bind each person independently. Reiterate relationship and blocking:

```text
@图片1的角色 A 始终位于画面左侧，穿深蓝外套；
@图片2的角色 B 始终位于画面右侧，穿米白风衣。
两人面部与服装特征互不混淆。
```

### Green screen

Specify solid green background, isolated subject, clean edges, whether contact shadows are allowed, and whether original camera/subject motion should be preserved.

### Seamless transition

Supply two source videos and describe the desired bridge: match cut, object occlusion, whip pan, morph, light flare, environmental continuation, or another transition. Name the visual anchor shared by both clips.

### Multi-panel storyboard

Use simple line art or stick-figure panels. State reading order and map each panel to framing, camera movement, action, and timing.

## Reliability notes

- More references are not automatically better. Use only references that control a necessary dimension.
- Complex physical actions, many characters, long reference clips, and long edit sources may need retries.
- Keep each time block achievable. A single 3-second interval should not contain several location changes, long dialogue, and complex choreography.
- For preservation-sensitive edits, explicitly list invariants.
- For extension, repeated generations may accumulate texture or identity drift; use clean identity references and restate continuity anchors.
- For ultra-long video, manage continuity at scene transitions and repeat only the few global facts that truly must persist.
