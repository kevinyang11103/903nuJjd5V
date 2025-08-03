# 💗圣地延安美食乐享系统💗

## 前言
> 💗工作室介绍：✌全网顾客1W+,CSDN全栈领域创作、b站/微信公众号/小红书/gitee等平台提供优质服务,计算机毕设实战导师。目前专注于大学生项目实战开发,讲解,毕业答疑辅导✌
> 💗主要服务内容：选题定题、开题报告、任务书、程序开发、文档编写和辅导、文档降重、程序讲解、答辩辅导等，欢迎咨询~
> 🌟文末获取源码+数据库+文档🌟 感兴趣的可以先收藏起来，还有大家在毕设选题，项目以及文档编写等相关问题都可以给我沟通，希望帮助更多的人
> 👇🏻在线演示 联系我们👇🏻
> [计算机毕设精品案例在线演示视频-5000套](https://www.yuque.com/yuqueyonghux32e1j/kxdc9g/ad8oz3bamkxmay0e#Cxun)
> 
> 🌟![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/429f9b4d85284ef39b31d818da6e39b1.png#pic_center)

## 内容介绍
圣地延安，作为中国革命的重要圣地和历史文化名城，不仅拥有丰富的红色旅游资源，还以其独特的美食文化吸引着众多游客和食客。然而，传统的美食推广方式往往受限于地域和时间，难以让更多人了解和品尝到延安的美食。因此，开发一个基于Spring Boot的圣地延安美食乐享系统显得尤为重要。该系统旨在通过互联网平台，将延安的美食文化推向更广泛的受众，同时提升游客的旅游体验，促进地方经济的发展。选题定题、开题报告、任务书、程序开发、文档编写和辅导、文档降重、程序讲解、答辩辅导等。

## 技术介绍
- 语言：Java
- 使用框架：Spring Boot
- 前端技术：JS、Vue、css3
- 开发工具：IDEA/Eclipse
- 数据库：MySQL 5.7/8.0
- 数据库管理工具：phpstudy/Navicat
- JDK版本：jdk1.8
- Maven: apache-maven 3.8.1-bin
- 前端环境：Node.Js 12\14\16

## 核心代码
```java
package com.example.controller;
import cn.hutool.core.util.StrUtil;
import cn.hutool.crypto.SecureUtil;
import com.example.common.Result;
import com.example.entity.User;
import com.example.mapper.UserMapper;
import com.example.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/user")
public class UserController {

    @Autowired
    private UserService userService;

    @Autowired
    private UserMapper userMapper;

    @PostMapping("/register")
    public Result register(@RequestBody User user) {
        if (StrUtil.isEmpty(user.getUsername()) || StrUtil.isEmpty(user.getPassword())) {
            return Result.fail("用户名或密码不能为空");
        }
        User existUser = userMapper.selectByUsername(user.getUsername());
        if (existUser != null) {
            return Result.fail("用户已存在");
        }
        user.setPassword(SecureUtil.md5(user.getPassword()));
        userMapper.insert(user);
        return Result.success("注册成功");
    }

    @PostMapping("/login")
    public Result login(@RequestBody User user) {
        if (StrUtil.isEmpty(user.getUsername()) || StrUtil.isEmpty(user.getPassword())) {
            return Result.fail("用户名或密码不能为空");
        }
        User existUser = userMapper.selectByUsername(user.getUsername());
        if (existUser == null) {
            return Result.fail("用户不存在");
        }
        if (!SecureUtil.md5(user.getPassword()).equals(existUser.getPassword())) {
            return Result.fail("密码错误");
        }
        return Result.success("登录成功", existUser);
    }
}
```

## 联系我们
🌟![在这里插入图片描述](https://github.com/user-attachments/assets/8f1ce2ba-72f1-441f-8d65-395ddab4650d)

## 免费源码获取

![下载](https://github.com/user-attachments/assets/2d103c9e-5ccc-44a1-a6d7-23a47c088dca)

## 项目截图
![screenshot_01](https://github.com/user-attachments/assets/25ad8884-3838-4205-b340-cc260df2958b)![screenshot_09](https://github.com/user-attachments/assets/ad559f05-697a-4270-85f5-27cd61ead919)
![screenshot_08](https://github.com/user-attachments/assets/62f3d241-0c95-41ac-81c9-836ded8b68ce)
![screenshot_07](https://github.com/user-attachments/assets/71071fef-684e-403f-9a29-f11027b741b6)
![screenshot_06](https://github.com/user-attachments/assets/3bc62d6d-ab57-4afe-9413-35013759736a)
![screenshot_05](https://github.com/user-attachments/assets/24828fa7-11d0-49f8-a7ad-eaf6753546fc)
![screenshot_04](https://github.com/user-attachments/assets/3fcc469c-dab3-478b-9f1a-d502bb77808d)
![screenshot_03](https://github.com/user-attachments/assets/aabab423-d570-4fa2-9973-3404168db01d)
![screenshot_02](https://github.com/user-attachments/assets/8694961e-4d3f-4c64-bc06-10df1b28d84b)

