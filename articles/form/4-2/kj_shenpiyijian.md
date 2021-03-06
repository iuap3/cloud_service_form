## **如何使用审批意见控件**



新上线的用友云表单增加了几个控件，其中一个叫做“审批意见“控件，它实现的功能是把审批人在审批过程中填写的审批意见回写到表单上。



具体应用场景：



![](/articles/form/4-2/images/image_spyj01.png)


图一



像图一请假单这样的人力行政类的审批单据，一般都会有在单据上显示出各级领导审批意见的要求。



我们通常给出的解决方案，比如：



1、 采用变通的解决方案，表单上不定义出这些字段，审批时直接输入意见，后续查看时，需要和审批历史一并查看；



这种方案的缺点：不直观



2、 在表单直接定义出这些字段，然后在相应的审批环节将其设置为可编辑，比如“部门经理审批”字段在部门经理审批环节设置为可编辑，将“分管领导审批”字段在分管领导审批环节设置为可编辑，当流程流转到这些环节时，直接在这些字段上填写意见；



这个方案的较上一方案的优点：直观，直接；



缺点：由于审批意见直接填写到表单上了，所以审批历史里没有相关记录；



3、 使用审批意见控件，表单上使用审批意见控件，与关联的流程环节对应起来，通过系统自动回写的功能，将用户在审批过程中填写的意见填写到表单的字段上；



优点：表单上回写的意见与审批历史一致



下面将着重介绍一下本版新上线的“审批意见”控件实现的功能。



**第一步：在表单设计器上设计表单，在部门经理审批、分管领导审批、人力资源部审批三个字段的位置拖入“审批意见”控件。**



审批控件位于“控件—系统”分类下面，如图二所示。用鼠标选中“审批意见”，按住鼠标右键，将其拖入设计器画布上想要放置的位置，点击控件标题旁边的小笔，可以修改控件的标题，比如，将图二中的“审批意见”修改为“人力资源部审批”。



![](/articles/form/4-2/images/image_spyj02.png)


图二



**第二步：为表单设计关联的流程**



用友云表单中的表单支持两大类应用场景，一类是数据收集的场景，另一类是关联流程的审批场景。



针对于关联流程的表单，系统支持两类流程，一类是自由流程，另一类是固定流程。我们的审批意见控件只适用于关联了固定流程的表单。

![](/articles/form/4-2/images/image_spyj03.png)


图三



如图三所示，选中标注为①的“关联流程”，并为要关联的流程定义一个名称，如“请假单流程0511”，然后点击下面的标注为②的“创建新流程”按钮。系统直接跳转到用友云审批中定义流程，如图四所示。

![](/articles/form/4-2/images/image_spyj04.png)

图四



在用友云审批中定义好流程后，点击界面上方的“暂存”按钮，只是把画布上设计好的流程保存起来了，但还不能发起流程，只有点击了“保存并发布”按钮后，设计的流程才真正启动可以发起了。



**第三步：保存表单。**



在用友云审批中定义好流程后，无论是点击了暂存按钮还是保存并发布按钮，我们只是把定义的流程做了一个保存，而表单和流程之前引用关系并没有保存起来 。此时我们需要点击一下图三中标记为③的保存或保存并启用按钮，将这种关系保存到表单上。



注意：新建流程之后的保存表单，这一点很重要。



**第四步：设置表单字段与流程环节的对应关系。**



选中审批意见控件，如图五中的部门经理审批，界面右侧显示该控件的属性，审批意见控件有两个关键属性：审批环节和意见格式。

![](/articles/form/4-2/images/image_spyj05.png)

图五



图五标记为①的位置用于定义审批环节，初始状态显示“请选择审批环节”，这里的审批环节取的是表单关联的固定流程中的环节，如这个例子中，就是“请假单流程0511”的流程环节。选中部门经理环节，界面如图六所示。



**第五步：设置审批意见的显示格式。**



控件定义了审批环节后，在审批环节下面会出现意见格式的属性，如图六标记为①的部分。系统默认意见格式为“审批结果+审批意见”，“审批人”、“审批时间”、“审批人所在部门”三项根据需要可选，点击标记为②的小图标，可以增加或删除选项。


![](/articles/form/4-2/images/image_spyj06.png)




图六



例如，部门经理环节，审批结果为同意，审批意见为：请安排好工作，审批人为常乐，审批人部门为研发部，审批时间为2017.5.11 10:00，系统可以显示为以下几种格式：



① 审批结果+审批意见：同意。意见：请安排好工作；



② 审批结果+审批意见+审批人：同意。意见：请安排好工作；常乐；



③ 审批结果+审批意见+审批人+审批人所在部门：同意。意见：请安排好工作；常乐；研发部；



④ 审批结果+审批意见+审批人+审批人所在部门+审批时间：同意。意见：请安排好工作；常乐；研发部；2017-5-11 10:00；



⑤ 审批人：常乐；



⑥ 审批时间：2017-5-11 10:00；



⑦ 审批人+审批时间：常乐；2017-5-11 10:00；



……



意见回写的项目及项目之间的顺序根据实际需要可调整 。定义好的审批意见如图七所示，点击设计器的保存或保存并启用，保存设置。



![](/articles/form/4-2/images/image_spyj07.png)




图七



回写后的效果如图八所示。


![](/articles/form/4-2/images/image_spyj08.png)




图八


