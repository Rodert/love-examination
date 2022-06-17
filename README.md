# love-examination
基于SSM+Bootstrap【爱校教务系统管理系统】附源码

**免费领取源码+参考论文** 基于SSM+Bootstrap【爱校教务系统管理系统】


> **博主介绍：** 🚀自媒体 JavaPub 独立维护人，全网粉丝15w+，csdn博客专家、java领域优质创作者，51ctoTOP10博主，知乎/掘金/华为云/阿里云/InfoQ等平台优质作者、专注于Java技术领域和副业。🚀
> 
> ---
> 
> **公众号：JavaPub** ⭐ ⭐简历模板、学习资料、面试题库等都给你💪
> 
>  ---
>  🍅 `文末获取源码` 🍅 **无套路，免费领取**
>  

> ## 前言介绍：


现如今学校招生越来越多,必然就会有大量的学生信息需要处理。如果只靠人力来完成,这将会变成一项非常繁琐、复杂的工作,而且还会出现很多意想不到的错误,给管理这些数据带来了很大的不便,也越来越不适合学校发展的需要.教务管理系统是一个庞大而复杂的系统,它包括对院系资料的管理,对课程资料的管理,对学生资料的管理和对学生成绩的管理等等主要的功能。教务管理系统是每个学校的一项必不可少的内容,它的好坏直接影响到学校里的主要工作,一旦此系统瘫疾,学校将会受到非常严重的损失,也会影响到每一个学生.



![在这里插入图片描述](https://img-blog.csdnimg.cn/5b9abf3ea7ab4281a325128e50924310.png)



一、行业发展缓慢的原因分析

所以现如今设计一个功能完整、操作简单以及界面友好的教务管理系统变得非常重要。

为了提高教务管理工作的效率,减少错误的出现,节约大量的人力资源,现在的学校的教务管理也逐步从手工转到计算机自动化信息处理阶段。

通过这个系统,用户可以方便的对院系资料、课程资料、学生资料和学生成绩资料进行添加、修改和删除操作,还可以对学生资料和成绩进行查询操作.除此之外,对用户的添加和删除操作也很方便


> ## 系统设计：


该项目是基于SSM+Bootstrap【爱校教务系统管理系统】，下面做了功能和相关技术的描述，适合出入职场和即将进入职场的各位，如有问题欢迎留言。

系统总共分为几个大的模块。


管理员可对 教师信息、学生信息、课程信息 进行 增删改查 操作，管理员账户，可以重置非管理员账户的密码 

* 课程管理：当课程已经有学生选课成功时，将不能删除 
* 学生管理：添加学生信息时，其信息也会添加到登录表中 
* 教师管理：同上 
* 账户密码重置： 
* 修改密码： 

教师登陆后，可以获取其，教授的课程列表，并可以给已经选择该课程的同学打分，无法对已经给完分的同学进行二次操作 
* 我的课程 
* 修改密码 


 学生登录后，根据学生信息，获取其已经选择的课程，和已经修完的课程 

* 所有课程: 在这里选修课程，选好后，将会自动跳转到已选课程选项 

* 已选课程: 这里显示的是，还没修完的课程，也就是老师还没给成绩，由于还没有给成绩，所以这里可以进行退课操作 

* 已修课程: 显示已经修完，老师已经给成绩的课程 

* 修改密码: 

一

**运行环境**

JDK8、Tomcat8、MySQL5.7、IntelliJ IDEA、Maven

- IOC容器：Spring Web框架：SpringMVC
- ORM框架：Mybatis
- 数据源：C3P0 
- 日志：log4j
- 前端框架：Bootstrap

---

![在这里插入图片描述](https://img-blog.csdnimg.cn/195df2aad236468eb37474805e7bcebb.png)

**账号：**

![Alt text]

管理员页：管理员账户：admin+123

![Alt text]

学生页：学生登录: 10001+123

![Alt text]

老师页：教师登录：1001+123


> ## 功能截图：

![在这里插入图片描述](https://img-blog.csdnimg.cn/ea6d5cb072b64475bd93e548d8e77a5d.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/4f682246cd3548bd955e83ce64c578ad.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/42cf329175b04113b6770b358e063c46.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/c77beeea40cf446892babb196c0db036.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/c0466cc6a0974866a0be81c87d46a26a.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/94f2fcdc442449ab98247ba3ab165631.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/151a471ee48f4baf80eaaa77c434c624.png)




> ## 代码实现：

```java


import java.io.IOException;

import javax.servlet.ServletConfig;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;


@WebServlet("/MyServlet")
public class MyServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    public MyServlet() {
        super();
    }

    @Override
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		System.out.println("doget MyServlet");
	}
    @Override
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    	System.out.println("dopost MyServlet");
    	super.doPost(request, response);
	}
    @Override
    public void init(ServletConfig servletConfig){
    	System.out.println("MyServlet");
    }

}

```

----

```java
package com.system.controller;

import com.system.exception.CustomException;
import com.system.po.*;
import com.system.service.*;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

import javax.annotation.Resource;
import java.util.List;

/**
 * Created by Jacey on 2017/6/30.
 */
@Controller
@RequestMapping("/admin")
public class AdminController {

	@Resource(name = "studentServiceImpl")
	private StudentService studentService;

	@Resource(name = "teacherServiceImpl")
	private TeacherService teacherService;

	@Resource(name = "courseServiceImpl")
	private CourseService courseService;

	@Resource(name = "collegeServiceImpl")
	private CollegeService collegeService;

	@Resource(name = "userloginServiceImpl")
	private UserloginService userloginService;

	/*
	 * <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<学生操作>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
	 * >>>>>
	 */

	// 学生信息显示
	@RequestMapping("/showStudent")
	public String showStudent(Model model, Integer page) throws Exception {

		List<StudentCustom> list = null;
		// 页码对象
		PagingVO pagingVO = new PagingVO();
		// 设置总页数
		pagingVO.setTotalCount(studentService.getCountStudent());
		if (page == null || page == 0) {
			pagingVO.setToPageNo(1);
			list = studentService.findByPaging(1);
		} else {
			pagingVO.setToPageNo(page);
			list = studentService.findByPaging(page);
		}

		model.addAttribute("studentList", list);
		model.addAttribute("pagingVO", pagingVO);

		return "admin/showStudent";

	}

	// 添加学生信息页面显示
	@RequestMapping(value = "/addStudent", method = { RequestMethod.GET })
	public String addStudentUI(Model model) throws Exception {

		List<College> list = collegeService.finAll();

		model.addAttribute("collegeList", list);

		return "admin/addStudent";
	}

	// 添加学生信息操作
	@RequestMapping(value = "/addStudent", method = { RequestMethod.POST })
	public String addStudent(StudentCustom studentCustom, Model model)
			throws Exception {

		Boolean result = studentService.save(studentCustom);

		if (!result) {
			model.addAttribute("message", "学号重复");
			return "error";
		}
		// 添加成功后，也添加到登录表
		Userlogin userlogin = new Userlogin();
		userlogin.setUsername(studentCustom.getUserid().toString());
		userlogin.setPassword("123");
		userlogin.setRole(2);
		userloginService.save(userlogin);

		// 重定向
		return "redirect:/admin/showStudent";
	}

	// 修改学生信息页面显示
	@RequestMapping(value = "/editStudent", method = { RequestMethod.GET })
	public String editStudentUI(Integer id, Model model) throws Exception {
		if (id == null) {
			// 加入没有带学生id就进来的话就返回学生显示页面
			return "redirect:/admin/showStudent";
		}
		StudentCustom studentCustom = studentService.findById(id);
		if (studentCustom == null) {
			throw new CustomException("未找到该名学生");
		}
		List<College> list = collegeService.finAll();

		model.addAttribute("collegeList", list);
		model.addAttribute("student", studentCustom);

		return "admin/editStudent";
	}

	// 修改学生信息处理
	@RequestMapping(value = "/editStudent", method = { RequestMethod.POST })
	public String editStudent(StudentCustom studentCustom) throws Exception {

		studentService.updataById(studentCustom.getUserid(), studentCustom);

		// 重定向
		return "redirect:/admin/showStudent";
	}

	// 删除学生
	@RequestMapping(value = "/removeStudent", method = { RequestMethod.GET })
	private String removeStudent(Integer id) throws Exception {
		if (id == null) {
			// 加入没有带学生id就进来的话就返回学生显示页面
			return "admin/showStudent";
		}
		studentService.removeById(id);
		userloginService.removeByName(id.toString());

		return "redirect:/admin/showStudent";
	}

	// 搜索学生
	@RequestMapping(value = "selectStudent", method = { RequestMethod.POST })
	private String selectStudent(String findByName, Model model)
			throws Exception {

		List<StudentCustom> list = studentService.findByName(findByName);

		model.addAttribute("studentList", list);
		return "admin/showStudent";
	}

	/*
	 * <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<教师操作>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
	 * >>>>>>>>
	 */

	// 教师页面显示
	@RequestMapping("/showTeacher")
	public String showTeacher(Model model, Integer page) throws Exception {

		List<TeacherCustom> list = null;
		// 页码对象
		PagingVO pagingVO = new PagingVO();
		// 设置总页数
		pagingVO.setTotalCount(teacherService.getCountTeacher());
		if (page == null || page == 0) {
			pagingVO.setToPageNo(1);
			list = teacherService.findByPaging(1);
		} else {
			pagingVO.setToPageNo(page);
			list = teacherService.findByPaging(page);
		}

		model.addAttribute("teacherList", list);
		model.addAttribute("pagingVO", pagingVO);

		return "admin/showTeacher";

	}

	// 添加教师信息
	@RequestMapping(value = "/addTeacher", method = { RequestMethod.GET })
	public String addTeacherUI(Model model) throws Exception {

		List<College> list = collegeService.finAll();

		model.addAttribute("collegeList", list);

		return "admin/addTeacher";
	}

	// 添加教师信息处理
	@RequestMapping(value = "/addTeacher", method = { RequestMethod.POST })
	public String addTeacher(TeacherCustom teacherCustom, Model model)
			throws Exception {

		Boolean result = teacherService.save(teacherCustom);

		if (!result) {
			model.addAttribute("message", "工号重复");
			return "error";
		}
		// 添加成功后，也添加到登录表
		Userlogin userlogin = new Userlogin();
		userlogin.setUsername(teacherCustom.getUserid().toString());
		userlogin.setPassword("123");
		userlogin.setRole(1);
		userloginService.save(userlogin);

		// 重定向
		return "redirect:/admin/showTeacher";
	}

	// 修改教师信息页面显示
	@RequestMapping(value = "/editTeacher", method = { RequestMethod.GET })
	public String editTeacherUI(Integer id, Model model) throws Exception {
		if (id == null) {
			return "redirect:/admin/showTeacher";
		}
		TeacherCustom teacherCustom = teacherService.findById(id);
		if (teacherCustom == null) {
			throw new CustomException("未找到该名学生");
		}
		List<College> list = collegeService.finAll();

		model.addAttribute("collegeList", list);
		model.addAttribute("teacher", teacherCustom);

		return "admin/editTeacher";
	}

	// 修改教师信息页面处理
	@RequestMapping(value = "/editTeacher", method = { RequestMethod.POST })
	public String editTeacher(TeacherCustom teacherCustom) throws Exception {

		teacherService.updateById(teacherCustom.getUserid(), teacherCustom);

		// 重定向
		return "redirect:/admin/showTeacher";
	}

	// 删除教师
	@RequestMapping("/removeTeacher")
	public String removeTeacher(Integer id) throws Exception {
		if (id == null) {
			// 加入没有带教师id就进来的话就返回教师显示页面
			return "admin/showTeacher";
		}
		teacherService.removeById(id);
		userloginService.removeByName(id.toString());

		return "redirect:/admin/showTeacher";
	}

	// 搜索教师
	@RequestMapping(value = "selectTeacher", method = { RequestMethod.POST })
	private String selectTeacher(String findByName, Model model)
			throws Exception {

		List<TeacherCustom> list = teacherService.findByName(findByName);

		model.addAttribute("teacherList", list);
		return "admin/showTeacher";
	}

	/*
	 * <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<课程操作>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
	 * >>>>>>>>
	 */

	// 课程信息显示
	@RequestMapping("/showCourse")
	public String showCourse(Model model, Integer page) throws Exception {

		List<CourseCustom> list = null;
		// 页码对象
		PagingVO pagingVO = new PagingVO();
		// 设置总页数
		pagingVO.setTotalCount(courseService.getCountCouse());
		if (page == null || page == 0) {
			pagingVO.setToPageNo(1);
			list = courseService.findByPaging(1);
		} else {
			pagingVO.setToPageNo(page);
			list = courseService.findByPaging(page);
		}

		model.addAttribute("courseList", list);
		model.addAttribute("pagingVO", pagingVO);

		return "/admin/showCourse";

	}

	// 添加课程
	@RequestMapping(value = "/addCourse", method = { RequestMethod.GET })
	public String addCourseUI(Model model) throws Exception {

		List<TeacherCustom> list = teacherService.findAll();
		List<College> collegeList = collegeService.finAll();

		model.addAttribute("collegeList", collegeList);
		model.addAttribute("teacherList", list);

		return "admin/addCourse";
	}

	// 添加课程信息处理
	@RequestMapping(value = "/addCourse", method = { RequestMethod.POST })
	public String addCourse(CourseCustom courseCustom, Model model)
			throws Exception {

		Boolean result = courseService.save(courseCustom);

		if (!result) {
			model.addAttribute("message", "课程号重复");
			return "error";
		}

		// 重定向
		return "redirect:/admin/showCourse";
	}

	// 修改教师信息页面显示
	@RequestMapping(value = "/editCourse", method = { RequestMethod.GET })
	public String editCourseUI(Integer id, Model model) throws Exception {
		if (id == null) {
			return "redirect:/admin/showCourse";
		}
		CourseCustom courseCustom = courseService.findById(id);
		if (courseCustom == null) {
			throw new CustomException("未找到该课程");
		}
		List<TeacherCustom> list = teacherService.findAll();
		List<College> collegeList = collegeService.finAll();

		model.addAttribute("teacherList", list);
		model.addAttribute("collegeList", collegeList);
		model.addAttribute("course", courseCustom);

		return "admin/editCourse";
	}

	// 修改教师信息页面处理
	@RequestMapping(value = "/editCourse", method = { RequestMethod.POST })
	public String editCourse(CourseCustom courseCustom) throws Exception {

		courseService.upadteById(courseCustom.getCourseid(), courseCustom);

		// 重定向
		return "redirect:/admin/showCourse";
	}

	// 删除课程信息
	@RequestMapping("/removeCourse")
	public String removeCourse(Integer id) throws Exception {
		if (id == null) {
			// 加入没有带教师id就进来的话就返回教师显示页面
			return "admin/showCourse";
		}
		courseService.removeById(id);

		return "redirect:/admin/showCourse";
	}

	// 搜索课程
	@RequestMapping(value = "selectCourse", method = { RequestMethod.POST })
	private String selectCourse(String findByName, Model model)
			throws Exception {

		List<CourseCustom> list = courseService.findByName(findByName);

		model.addAttribute("courseList", list);
		return "admin/showCourse";
	}

	/*
	 * <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<其他操作>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
	 * >>>>>>>>
	 */

	// 普通用户账号密码重置
	@RequestMapping("/userPasswordRest")
	public String userPasswordRestUI() throws Exception {
		return "admin/userPasswordRest";
	}

	// 普通用户账号密码重置处理
	@RequestMapping(value = "/userPasswordRest", method = { RequestMethod.POST })
	public String userPasswordRest(Userlogin userlogin) throws Exception {

		Userlogin u = userloginService.findByName(userlogin.getUsername());

		if (u != null) {
			if (u.getRole() == 0) {
				throw new CustomException("该账户为管理员账户，没法修改");
			}
			u.setPassword(userlogin.getPassword());
			userloginService.updateByName(userlogin.getUsername(), u);
		} else {
			throw new CustomException("没找到该用户");
		}

		return "admin/userPasswordRest";
	}

	// 本账户密码重置
	@RequestMapping("/passwordRest")
	public String passwordRestUI() throws Exception {
		return "admin/passwordRest";
	}

}

```

---

```java
package com.system.controller;

import com.system.po.Userlogin;
import org.apache.shiro.SecurityUtils;
import org.apache.shiro.authc.UsernamePasswordToken;
import org.apache.shiro.subject.Subject;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

/**
 * Created by Jacey on 2017/6/30.
 */
@Controller
public class LoginController {

    //登录跳转
    @RequestMapping(value = "/login", method = {RequestMethod.GET})
    public String loginUI() throws Exception {
        return "../../login";
    }

    //登录表单处理
    @RequestMapping(value = "/login", method = {RequestMethod.POST})
    public String login(Userlogin userlogin) throws Exception {

        //Shiro实现登录
        UsernamePasswordToken token = new UsernamePasswordToken(userlogin.getUsername(),
                userlogin.getPassword());
        Subject subject = SecurityUtils.getSubject();

        //如果获取不到用户名就是登录失败，但登录失败的话，会直接抛出异常
        subject.login(token);

        if (subject.hasRole("admin")) {
            return "redirect:/admin/showStudent";
        } else if (subject.hasRole("teacher")) {
            return "redirect:/teacher/showCourse";
        } else if (subject.hasRole("student")) {
            return "redirect:/student/showCourse";
        }

        return "/login";
    }

}

```

---

```java
package com.system.controller;

import com.system.exception.CustomException;
import com.system.po.Userlogin;
import com.system.service.UserloginService;
import org.apache.shiro.SecurityUtils;
import org.apache.shiro.subject.Subject;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

import javax.annotation.Resource;

/**
 * Created by Jacey on 2017/7/6.
 */
@Controller
public class RestPasswordController {

    @Resource(name = "userloginServiceImpl")
    private UserloginService userloginService;

    // 本账户密码重置
    @RequestMapping(value = "/passwordRest", method = {RequestMethod.POST})
    public String passwordRest(String oldPassword, String password1) throws Exception {
        Subject subject = SecurityUtils.getSubject();
        String username = (String) subject.getPrincipal();

        Userlogin userlogin = userloginService.findByName(username);

        if (!oldPassword.equals(userlogin.getPassword())) {
            throw new CustomException("旧密码不正确");
        } else {
            userlogin.setPassword(password1);
            userloginService.updateByName(username, userlogin);
        }

        return "redirect:/logout";
    }

}

```

---

> ## 论文参考：


![在这里插入图片描述](https://img-blog.csdnimg.cn/864963dc60414723bfefa961108e2e4b.png)



> ### 源码获取:
> 
>  大家`点赞、收藏、关注、评论`啦 、查看👇🏻👇🏻👇🏻`微信`公众号获取联系方式👇🏻👇🏻👇🏻
> 
> 公众号回复：[爱校教务系统管理系统]
> 
> ---
> 
>  打卡 文章 `更新 3 /  365天`
> 
> ---
> 
>  **精彩专栏推荐订阅：在下方专栏**👇🏻👇🏻👇🏻👇🏻
> 
> ---
> 
> [Java项目精品实战案例《101套》](https://blog.csdn.net/qq_40374604/category_11788364.html)
> 
> ---
> 
> [web前端期末大作业网页实战《365套》](https://blog.csdn.net/qq_40374604/category_11789121.html)
> 



![](https://img-blog.csdnimg.cn/f0dfc15b686e4c18bfcbddc702464327.gif#pic_center)

<center>
 <font face="黑体" color="red" size="4">关注公众号，回复1024，获取Java学习路线思维导图、加入源码计划学习交流群</font> 
</center>




![公众号：JavaPub](https://img-blog.csdnimg.cn/20210218233243678.jpg#pic_center)


---



## 推荐阅读（附源码-附安装视频）

`无套路，免费领取`



中国象棋：[下载地址1](https://javapub.blog.csdn.net/article/details/124503370) | [下载地址2](http://javapub.net.cn/project/game/chinese-chess-game.html)

植物大战僵尸：[下载地址1](https://javapub.blog.csdn.net/article/details/124238828) | [下载地址2](http://javapub.net.cn/project/game/plants-vs-zombies-game.html)

俄罗斯方块：[下载地址1](https://javapub.blog.csdn.net/article/details/124471774) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

超级马里奥：[下载地址1](https://javapub.blog.csdn.net/article/details/124463555) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

吃豆人游戏：[下载地址1](https://javapub.blog.csdn.net/article/details/124463461) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

打地鼠：[下载地址1](https://javapub.blog.csdn.net/article/details/124463376) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

捕鱼达人：[下载地址1](https://javapub.blog.csdn.net/article/details/123834030) | [下载地址2](http://javapub.net.cn/project/game/catch-fish-game.html)

打飞机：[下载地址1](https://javapub.blog.csdn.net/article/details/123699508) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

坦克大战：[下载地址1](https://javapub.blog.csdn.net/article/details/123779963) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

1024：[下载地址1](https://javapub.blog.csdn.net/article/details/123832950) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

贪吃蛇：[下载地址1](https://javapub.blog.csdn.net/article/details/123833575) | [下载地址2](http://javapub.net.cn/project/game/super-mario-game.html)

3D赛车：[下载地址1](https://javapub.blog.csdn.net/article/details/124462822) | [下载地址2](http://javapub.net.cn/project/game/3d-racing-game.html)




汇总地址：[下载地址1](https://blog.csdn.net/qq_40374604/category_11788364.html) | [下载地址2](http://javapub.net.cn/category/%E5%B0%8F%E6%B8%B8%E6%88%8F/)



## 当前目录：

0. [ssm_helloworld_web 【SSM整合】](ssm_helloworld_web)
0. [firstSpringProject 【spring初始化工程】](firstSpringProject)
1. [springbootfirstdemo 【springboot入门初始化】](https://github.com/Rodert/SpringBoot-javapub/tree/main/springbootfirstdemo)
2. [spring-boot整合MyBatis批量更新](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-mybatis)
3. [spring-boot自定义注解+AOP切面日志](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-annotation )
4. [spring-boot整合docker打包jar](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-docker)
5. [spring-boot 整合elasticsearch手脚架](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-elasticsearch)
6. [spring-boot整合解析excel](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-excel)
7. [spring-boot实现全链路日志traceId](https://github.com/Rodert/SpringBoot-javapub/tree/main/spring-boot-trace)
8. [springboot整合flowable工作流](https://github.com/Rodert/springboot-flowable)   [GitHub](https://github.com/Rodert/springboot-flowable) | [Gitee](https://gitee.com/rodert/springboot-flowable)
9. [SpringBoot+Vue后台管理系统【源码+视频】](https://gitee.com/rodert/liawan-vue) [github](https://github.com/Rodert/liawan-vue) | [gitee](https://gitee.com/rodert/liawan-vue)
10. 


