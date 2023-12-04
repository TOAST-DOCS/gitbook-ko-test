## AI Service > Pose Estimation > 콘솔 사용 가이드

콘솔에 이미지 파일을 올려 모든 사람 영역을 인식하고, 해당 영역의 인체 관절 위치 정보를 얻을 수 있습니다.

## Pose Estimation

### 분석을 위한 사진 업로드

분석할 이미지를 업로드합니다.

- 이미지는 다음 2가지 방법으로 업로드할 수 있습니다.
    1. **이미지 업로드** 버튼 클릭
    2. 이미지 드래그 앤드 드롭

### 분석

사진을 업로드한 후 **분석** 버튼을 클릭하면 분석 결과가 화면 오른쪽에 JSON 형태로 나타납니다.

* [fileType] 파일 확장자(.jpg, .png)
* [numberOfPerson] 인식 결과 인원 수
* [keyPointList] 인식된 사람 목록
    * [personId] 인식 결과 구분을 위해 부여된 ID
    * [inferKeypointList] 인식된 신체 부위 목록
        * [name] 신체 부위 이름
        * [part] 신체 부위가 속한 부분 이름(body, foot, face, hand)
        * [ x ] x 좌표
        * [ y ] y 좌표
        * [score] 인식 결과에 대한 신뢰도


```json
{
  "fileType": "png",
  "numberOfPerson": 5,
  "keyPointList": [
    {
      "personId": "0",
      "inferKeypointList": [
        {
          "name": "nose",
          "part": "body",
          "x": 367.151489,
          "y": 79.552887,
          "score": 0.976
        },
        {
          "name": "left_eye",
          "part": "body",
          "x": 373.819214,
          "y": 73.5605469,
          "score": 0.985
        },
        ...
      ]
    },
    ...
    {
      "personId": 2,
      "inferKeypoints": [
        {
          "name": "nose",
          "part": "body",
          "x": 98.7361755,
          "y": 68.2939758,
          "score": 0.979
        },
        {
          "name": "left_eye",
          "part": "body",
          "x": 110.171448,
          "y": 56.0753479,
          "score": 0.983
        },
        ...
      ]
    },
  ]
}
```

* 분석 결과 복사 및 다운로드(JSON) 기능을 제공합니다.
