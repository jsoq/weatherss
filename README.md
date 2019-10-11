<h1 align="center"> weather </h1>

<p align="center"> A weather SDK..</p>


## Installing

```shell
$ composer require jsom/weather -vvv
```

## Usage
### 配置
    在使用本扩展之前，你需要去 高德开放平台 注册账号，然后创建应用，获取应用的 API Key。
### 使用
    ```php
        use Jsom\Weather\Weather;

        $key = 'xxxxxxxxxxxxxxxxxxxxxxxxxxx';

        $weather = new Weather($key);
    ```
### 获取实时天气
    ```php
        $response = $weather->getWeather('深圳');
    ```
    示例:
    ```php
        {
            "status": "1",
            "count": "1",
            "info": "OK",
            "infocode": "10000",
            "lives": [
                {
                    "province": "广东",
                    "city": "深圳市",
                    "adcode": "440300",
                    "weather": "中雨",
                    "temperature": "27",
                    "winddirection": "西南",
                    "windpower": "5",
                    "humidity": "94",
                    "reporttime": "2018-08-21 16:00:00"
                }
            ]
        }
    ```
### 获取近期天气预报
   ```
     $response = $weather->getWeather('深圳', 'all');
   ``` 
   示例：
   ```php
        {
            "status": "1", 
            "count": "1", 
            "info": "OK", 
            "infocode": "10000", 
            "forecasts": [
                {
                    "city": "深圳市", 
                    "adcode": "440300", 
                    "province": "广东", 
                    "reporttime": "2018-08-21 11:00:00", 
                    "casts": [
                        {
                            "date": "2018-08-21", 
                            "week": "2", 
                            "dayweather": "雷阵雨", 
                            "nightweather": "雷阵雨", 
                            "daytemp": "31", 
                            "nighttemp": "26", 
                            "daywind": "无风向", 
                            "nightwind": "无风向", 
                            "daypower": "≤3", 
                            "nightpower": "≤3"
                        }, 
                        {
                            "date": "2018-08-22", 
                            "week": "3", 
                            "dayweather": "雷阵雨", 
                            "nightweather": "雷阵雨", 
                            "daytemp": "32", 
                            "nighttemp": "27", 
                            "daywind": "无风向", 
                            "nightwind": "无风向", 
                            "daypower": "≤3", 
                            "nightpower": "≤3"
                        }, 
                        {
                            "date": "2018-08-23", 
                            "week": "4", 
                            "dayweather": "雷阵雨", 
                            "nightweather": "雷阵雨", 
                            "daytemp": "32", 
                            "nighttemp": "26", 
                            "daywind": "无风向", 
                            "nightwind": "无风向", 
                            "daypower": "≤3", 
                            "nightpower": "≤3"
                        }, 
                        {
                            "date": "2018-08-24", 
                            "week": "5", 
                            "dayweather": "雷阵雨", 
                            "nightweather": "雷阵雨", 
                            "daytemp": "31", 
                            "nighttemp": "26", 
                            "daywind": "无风向", 
                            "nightwind": "无风向", 
                            "daypower": "≤3", 
                            "nightpower": "≤3"
                        }
                    ]
                }
            ]
        }
   ```
### 获取 XML 格式返回值
    第三个参数为返回值类型，可选 json 与 xml，默认 json：
    ```
        $response = $weather->getWeather('深圳', 'all', 'xml');
    ```
    示例:
    ```
         <response>
            <status>1</status>
            <count>1</count>
            <info>OK</info>
            <infocode>10000</infocode>
            <lives type="list">
                <live>
                    <province>广东</province>
                    <city>深圳市</city>
                    <adcode>440300</adcode>
                    <weather>中雨</weather>
                    <temperature>27</temperature>
                    <winddirection>西南</winddirection>
                    <windpower>5</windpower>
                    <humidity>94</humidity>
                    <reporttime>2018-08-21 16:00:00</reporttime>
                </live>
            </lives>
        </response>
    ```



## Contributing

You can contribute in one of three ways:

1. File bug reports using the [issue tracker](https://github.com/jsom/weather/issues).
2. Answer questions or fix bugs on the [issue tracker](https://github.com/jsom/weather/issues).
3. Contribute new features or update the wiki.

_The code contribution process is not very formal. You just need to make sure that you follow the PSR-0, PSR-1, and PSR-2 coding guidelines. Any new code contributions must be accompanied by unit tests where applicable._

## License

MIT