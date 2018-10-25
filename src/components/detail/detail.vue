<template>
  <div class="detail">
      <goodslist @goto="goto"></goodslist>
      <contain :txt="txt"></contain>
  </div>
</template>
  
<script>
import goodslist from './goodslist'
import contain from './contain'
  
export default {
  components: {
    goodslist,
    contain
  },
  data(){
    return{
      details:[
        [
          [
            ['手机通讯','全部','iOS','Android','其他','二手手机'],
            ['品牌：','全部','小米（MI）','诺基亚（NOKIA）','苹果（Apple）','华为（HUAWEI）','LG','小米（MI）','HTC','诺基亚（NOKIA）','华为（HUAWEI）']
          ],
          [  
            ['/static/img/details/phone/pho1.jpg','Apple iPhone 8 Plus 国行正品 4G智能手机 深空灰 64G 全网通','5599','219.67'],
            ['/static/img/details/phone/pho2.jpg','Apple iPhone 8 Plus 国行正品 4G智能手机 红色特别版 64G 全网','5999','235.36'],
            ['/static/img/details/phone/pho3.jpg','Apple iPhone 8 Plus 国行正品 4G智能手机 金色 64G 全网通','5799','219.24'],
            ['/static/img/details/phone/pho4.jpg','Apple iPhone X 国行正品 4G智能手机 深空灰 64G 全网通','7499','286.37'],
            ['/static/img/details/phone/pho5.jpg','Apple iPhone X 国行正品 4G智能手机 银色 64G 全网通','7499','286.37'],
            ['/static/img/details/phone/pho6.jpg','Apple iPhone 8 国行正品 4G智能手机 红色特别版 64G 全网通','4799','188.28'],
            ['/static/img/details/phone/pho7.jpg','小米8 全网通4G手机 黑色 6GB+128GB','2899','113.74'],
            ['/static/img/details/phone/pho8.jpg','荣耀9i 移动联通电信4G全面屏手机 幻夜黑 4G+64G','1399','54.89'],
            ['/static/img/details/phone/pho9.jpg','荣耀9i 移动联通电信4G全面屏手机 魅海蓝 4G+64G','1399','50.97'],
            ['/static/img/details/phone/pho10.jpg','【限时12期免息】vivo NEX 零界全面屏AI双摄移动联通电信全','4498','168.63'],
            ['/static/img/details/phone/pho11.jpg','【限时12期免息】 vivoX23 旗舰新品 全网通 游戏手机 AI非凡摄','3498','137.24'],
            ['/static/img/details/phone/pho12.jpg','苹果（Apple）iPhone XS全网通国行正品 金色 64GB','10699','341.29'],
            ['/static/img/details/phone/pho13.jpg','苹果（Apple）iPhone XS Max双卡双待全网通国行正品 深空灰色','12999','431.53'],
            ['/static/img/details/phone/pho14.jpg','苹果（Apple）iPhone XS Max双卡双待全网通国行正品 金色','12999','431.53'],
            ['/static/img/details/phone/pho15.jpg','苹果（Apple）iPhone XS Max双卡双待全网通国行正品 银色','12999','431.53'],
            ['/static/img/details/phone/pho16.jpg','【限时12期免息】OPPO R17 2500万美颜拍照 6.4英寸水滴屏','3499','137.28'],
            ['/static/img/details/phone/pho17.jpg','【直降400】华为 HUAWEI P20 AI智慧全面屏 移动联通电信4G','3288','129'],
            ['/static/img/details/phone/pho18.jpg','【限时12期免息】 vivoX23 旗舰新品 全网通 游戏手机 AI非凡摄','3498','137.24'],
            ['/static/img/details/phone/pho19.jpg','【限时3期免息】小米8SE 全面屏智能手机 全网通4G 双卡双待','1699','66.66'],
            ['/static/img/details/phone/pho20.jpg','【6期免息】OPPO Find X曲面全景屏手机 全网通 全隐藏式3D摄','4999','196.13'],
            ['/static/img/details/phone/pho21.jpg','【12期免息】vivo X21 全面屏 双摄美颜拍照手机全网通4G手机','2498','98.01'],
            ['/static/img/details/phone/pho22.jpg','【限时送赠】荣耀10 全面屏AI摄影手机 全网通 移动联通电信4G','2299','90.20'],
            ['/static/img/details/phone/pho23.jpg','【限时12期免息】OPPO R17 2500万美颜拍照 6.4英寸水滴屏 光感屏幕指纹 全网通 移动联通','3599','141.20'],
            ['/static/img/details/phone/pho24.jpg','Apple iPhone 8 国行正品 4G智能手机 深空灰 64G 全网通','4699','183.93'],
            ['/static/img/details/phone/pho25.jpg','【限时3期免息】小米MIX 2S 全面屏 全网通4G游戏手机 黑色','2699','105.89'],
            ['/static/img/details/phone/pho26.jpg','【直降400】华为 HUAWEI P20 AI智慧全面屏 移动联通电信4G手机','3288','129'],
            ['/static/img/details/phone/pho27.jpg','【限时12期免息】vivo Z1 新一代全面屏AI双摄手机 移动联通电信','1898','70.55'],
            ['/static/img/details/phone/pho28.jpg','【限时12期免息】OPPO R17 2500万美颜拍照 6.4英寸水滴屏','3499','137.28'],
            ['/static/img/details/phone/pho29.jpg','【6期免息】一加手机6全面屏双摄游戏全网通4G手机 亮瓷黑','3599','141.20'],
            ['/static/img/details/phone/pho30.jpg','小米8 全网通4G手机 蓝色 6GB+128GB','2899','113.74'],
            ['/static/img/details/phone/pho31.jpg','【6期免息】OPPO Find X曲面全景屏手机 全网通 全隐藏式3D摄','4999','196.13'],
            ['/static/img/details/phone/pho32.jpg','Apple iPhone 8 国行正品 4G智能手机 金色 64G 全网通','4599','180.44'],
            ['/static/img/details/phone/pho33.jpg','小米6X 全网通4G 双卡双待智能手机 曜石黑 4GB 64GB','1349','48.77'],
            ['/static/img/details/phone/pho34.jpg','荣耀8X Max 珍珠屏 移动联通电信4G全面屏手机 双卡双待 幻夜','1499','58.82'],
            ['/static/img/details/phone/pho35.jpg','华为 HUAWEI nova 3 全网通移动联通电信4G手机 双卡双待 亮','2999','117.66'],
            ['/static/img/details/phone/pho36.jpg','iPhone 7 Plus 国行正品 全网通4G手机 亮黑色 128G 全网通','5499','215.75']
          ]
        ],
        [
          [
            ['腕带配饰','全部','智能/运动手表','瑞士手表','欧美手表','日韩手表','国产手表','智能/运动手表','表带配件','名品配饰','时尚配饰','闹钟挂钟'],
            ['品牌：','全部','安普里奥·阿玛尼(Emporio Armani)','佳明GARMIN','安普里奥·阿玛尼(Emporio Armani)','颂拓(SUUNTO)','New Balance','仕博达（SPORTSTAR）']
          ],
          [  
            ['/static/img/details/watch/watch1.jpg','【正品保质 假一赔十】卡西欧(casio)男士手表 g-shock系列运','2490','54.94'],
            ['/static/img/details/watch/watch2.jpg','丹尼尔惠灵顿（Daniel Wellington）进口DW手表时尚尼','1250','51.71'],
            ['/static/img/details/watch/watch3.jpg','丹尼尔惠灵顿（Daniel Wellington）进口DW女士手表时','1380 ','57.09'],
            ['/static/img/details/watch/watch4.jpg','丹尼尔惠灵顿（Daniel Wellington）DW潮流进口男士手','1450','59.98'],
            ['/static/img/details/watch/watch5.jpg','【正品保障 三年店保】卡西欧(CASIO)男士手表 防水石英男表','695','28.75'],
            ['/static/img/details/watch/watch6.jpg','丹尼尔惠灵顿（Daniel Wellington）新品dw进口潮流米','1290','53.36'],
            ['/static/img/details/watch/watch7.jpg','【领券立减150元 12期以内免息 下单送清洁套装4件套】天梭','3499','144.74'],
            ['/static/img/details/watch/watch8.jpg','丹尼尔惠灵顿（Daniel Wellington）DW手表进口不锈钢','1390','57.50'],
            ['/static/img/details/watch/watch9.jpg','【官方】卡西欧(CASIO)旗舰店 运动手表 夜跑防震防水石英女表','1290','45.34'],
            ['/static/img/details/watch/watch10.jpg','【唐艺昕同款】ADEXE SISTINE系列凹陷表盘手表女时尚简约玫','799','33.05'],
            ['/static/img/details/watch/watch11.jpg','【官方】卡西欧(CASIO)旗舰店 商务手表男皮带休闲防水男士石','890','21.47'],
            ['/static/img/details/watch/watch12.jpg','【12期免息 领劵立减】天梭(TISSOT)手表俊雅系列时尚石英','1699','66.15'],
            ['/static/img/details/watch/watch13.jpg','丹尼尔惠灵顿（Daniel Wellington）DW瑞典进口时尚皮','1490','61.64'],
            ['/static/img/details/watch/watch14.jpg','【正品保证 假一罚十】卡西欧(CASIO)手表 G-SHOCK系列丛林','999','32.23'],
            ['/static/img/details/watch/watch15.jpg','【正品保障 假一赔十】 卡西欧(CASIO)男表 5马达太阳能多功能','1358','53.74'],
            ['/static/img/details/watch/watch16.jpg','【官方旗舰店 12期以内免息】美国TIMEX/天美时手表男简约时','529','21.89'],
            ['/static/img/details/watch/watch17.jpg','Armani 阿玛尼潮流欧美时尚休闲皮带男表复古简约手表男','1990','74'],
            ['/static/img/details/watch/watch18.jpg','天王TIAN WANG时尚简约人气情侣表石英男表3874 黑色','520','20.65'],
            ['/static/img/details/watch/watch19.jpg','丹尼尔惠灵顿（Daniel Wellington）DW进口女士金属表','1780','73.63'],
            ['/static/img/details/watch/watch20.jpg','丹尼尔惠灵顿（Daniel Wellington）DW进口时尚学院织','1350','55.85'],
            ['/static/img/details/watch/watch21.jpg','Armani阿玛尼手表男新款时尚潮流镂空机械表简约欧美风皮带男','3990','119.92'],
            ['/static/img/details/watch/watch22.jpg','【正品保障 店保3年】卡西欧(CASIO) BABY-G潮流运动双显电','839','34.71'],
            ['/static/img/details/watch/watch23.jpg','丹尼尔惠灵顿（Daniel Wellington）进口DW男士手表经典简约皮带石英男表','1490','61.64'],
            ['/static/img/details/watch/watch24.jpg','【正品保质 假一罚十】卡西欧(CASIO)男士手表 商务防水计时','528','21.84'],
            ['/static/img/details/watch/watch25.jpg','天王TIAN WANG时尚简约人气情侣表石英男表3874 白色','520','20.65'],
            ['/static/img/details/watch/watch26.jpg','卡西欧(CASIO)手表 防水运动石英男表MTP-1183E-7A MTP','199','8.24'],
            ['/static/img/details/watch/watch27.jpg','ARMANI 阿玛尼手表休闲简约手表男时尚多功能日历石英男表','1990','74'],
            ['/static/img/details/watch/watch28.jpg','英国Superdry极度干燥 运动潮牌Urban系列日本精工机芯休闲','435','18'],
            ['/static/img/details/watch/watch29.jpg','卡西欧(CASIO)手表 G-SHOCK系列男表双显电子男表GA-100','769','31.81'],
            ['/static/img/details/watch/watch30.jpg','天王TIAN WANG正品男士手表经典商务钢带表大气沉稳自动机械','1449','57.87'],
            ['/static/img/details/watch/watch31.jpg','【官方】卡西欧(CASIO)旗舰店 G-SHOCK主题系列时尚街头运动','1090','45.09'],
            ['/static/img/details/watch/watch32.jpg','【12期免息 领劵立减】天梭(TISSOT)手表 力洛克系列机械男','3299','130.67'],
            ['/static/img/details/watch/watch33.jpg','天王TIAN WANG时尚简约人气情侣表石英男表3874 棕色','520','20.65'],
            ['/static/img/details/watch/watch34.jpg','丹尼尔惠灵顿（Daniel Wellington）DW手表欧美进口简约时尚男士手表石英表','1490','61.64'],
            ['/static/img/details/watch/watch35.jpg','丹尼尔惠灵顿（Daniel Wellington）DW手表进口不锈钢','1390','57.50'],
            ['/static/img/details/watch/watch36.jpg','【前任3于文文同款】ADEXE THE MEEK系列罗马刻度时尚玫','799','33.05']
          ]
        ],
        [  
          [
            ['电脑办公','全部','电脑整机','电脑配件','办公设备'],  
            ['品牌：','全部','AMD','小米（MI）','英特尔（Intel）','神舟（HASEE）','华硕（ASUS）','微星（MSI）','技嘉（GIGABYTE）','影驰（Galaxy）','蓝宝石（Sapphire）']
          ],
          [  
            ['/static/img/details/computer/computer1.jpg','惠普（HP）光影精灵傲腾版15.6英寸 酷睿八代i5 GTX1050吃鸡','5299','206.78'],
            ['/static/img/details/computer/computer2.jpg','惠普（HP）暗影精灵4代 游戏笔记本电脑 【GTX1050Ti】八代i5 8G 双硬盘','6499','254.98'],
            ['/static/img/details/computer/computer3.jpg','惠普（HP）畅游人Pavilion15 15.6英寸四核固态独显多彩轻薄','4399','181.96'],
            ['/static/img/details/computer/computer4.jpg','【新品】惠普（HP）光影精灵4 15.6英寸游戏本笔记本电脑','5199','215.05'],
            ['/static/img/details/computer/computer5.jpg','惠普（HP）战66 Pro G1 14英寸轻薄笔记本电脑 i5-8250U 8G','5299','184.36'],
            ['/static/img/details/computer/computer6.jpg','【新品】惠普（HP） 星14系列 星15系列微边框多彩轻薄笔记本','5499','227.46'],
            ['/static/img/details/computer/computer7.jpg','惠普（HP）小欧14英寸固态独显轻薄办公学习用笔记本电脑','2299','95.10'],
            ['/static/img/details/computer/computer8.jpg','惠普 （HP） 星 系列 14英寸时尚轻薄微边框笔记本电脑 i5','5399','223.33'],
            ['/static/img/details/computer/computer9.jpg','惠普（HP）光影精灵4 暗影精灵 15.6英寸吃鸡游戏笔记本电脑 白','6299','260.55'],
            ['/static/img/details/computer/computer10.jpg','惠普（HP）小欧 15.6英寸轻薄商用办公家用学生笔记本电脑','3099','128.19'],
            ['/static/img/details/computer/computer11.jpg','惠普 （HP）星14 系列窄边框多彩轻薄笔记本电脑 粉色 i7','6799','281.24'],
            ['/static/img/details/computer/computer12.jpg','惠普（HP）畅游人 星15系列 15.6英寸轻薄便携笔记本电脑 i5-8250U','4899','202.65'],
            ['/static/img/details/computer/computer13.jpg','惠普（HP）暗影精灵3代 15.6英寸游戏笔记本电脑 暗影精灵','7799','322.60'],
            ['/static/img/details/computer/computer14.jpg','【京东配送】惠普（HP）窄边框6.3mm纤薄IPS屏广视角金属底','1199','47.05'],
            ['/static/img/details/computer/computer15.jpg','【新品】惠普（HP）暗影精灵4代 4代Plus游戏笔记本电脑8代酷','6999','289.51'],
            ['/static/img/details/computer/computer16.jpg','惠普（HP）薄锐ENVY13系列 13.3英寸超轻薄窄边框金属笔','7499','310.19'],
            ['/static/img/details/computer/computer17.jpg','惠普（HP）暗影精灵4代 15.6英寸微边框 游戏本笔记本电脑','7699','318.46'],
            ['/static/img/details/computer/computer18.jpg','惠普 （HP） 星 系列 15.6英寸时尚轻薄微边框笔记本电脑','5799','239.87'],
            ['/static/img/details/computer/computer19.jpg','惠普（HP）小欧14英寸固态独显轻薄笔记本电脑 HP14g','2999','124.05'],
            ['/static/img/details/computer/computer20.jpg','惠普（HP）暗影精灵II代 15.6英寸游戏笔记本 i5 4G 1T','4999','196.13'],
            ['/static/img/details/computer/computer21.jpg','惠普(HP) 暗影精灵II代PLUS 17.3英寸游戏笔记本 i7-6700HQ','8949','351.10'],
            ['/static/img/details/computer/computer22.jpg','惠普（HP）幻系列 Elite Slice模块化办公电脑主机/套机','599','23.51'],
            ['/static/img/details/computer/computer23.jpg','惠普（HP）幻系列 Elite Slice模块化办公电脑主机/套机','199','7.81'],
            ['/static/img/details/computer/computer24.jpg','惠普（HP）幻系列 Elite Slice模块化办公电脑主机/套机','599','23.51'],
            ['/static/img/details/computer/computer25.jpg','惠普(HP)暗影精灵II代Pro 15.6英寸游戏笔记本（独显 IPS FHD暗','5199','203.98'],
            ['/static/img/details/computer/computer26.jpg','惠普（HP）暗影精灵 870系列 游戏台式主机（Win10） i5','6999','274.60'],
            ['/static/img/details/computer/computer27.jpg','Pavilion Wave系列 惠普畅游人革新艺术之作 i5 128G SSD +1T','6199','243.21'],
            ['/static/img/details/computer/computer28.jpg','惠普(HP)畅游人Pavilion 纤薄一体机（IPS FHD Win10） i5','7299','286.37'],
            ['/static/img/details/computer/computer29.jpg','小欧270系列 台式电脑 赛扬 4G 500G 19.5英寸','2299','90.20'],
            ['/static/img/details/computer/computer30.jpg','小欧270系列 台式电脑 i3 4G 1T 2G独显 23英寸','4499','176.51'],
            ['/static/img/details/computer/computer31.jpg','惠普（HP）暗影精灵 870系列 游戏台式主机（Win10） i5','6999','274.60'],
            ['/static/img/details/computer/computer32.jpg','惠普（HP）暗影精灵 870系列 游戏台式主机（Win10） i5','6999','274.60'],
            ['/static/img/details/computer/computer33.jpg','Pavilion畅游人 570系列 游戏台式主机 i5-7400 8G 1T GTX 1050','5499','215.75'],
            ['/static/img/details/computer/computer34.jpg','惠普（HP）暗影精灵III代 15.6英寸游戏笔记本电脑 i5','5799','227.52'],
            ['/static/img/details/computer/computer35.jpg','惠普（HP）HP14系列 14英寸笔记本电脑 银色 i5 8G 1T R5 IPS','4299','168.67'],
            ['/static/img/details/computer/computer36.jpg','惠普（HP）畅游人Pavilion 14英寸轻薄笔记本 银色 i5-7200U 4G','4799','188.28']
          ]
        ],
        [  
          [
            ['相机单反','全部','相机配件','摄影摄像'],  
            ['品牌：','全部','苹果（Apple）','小米（MI）','HTC','诺基亚（NOKIA）','华为（HUAWEI）','OPPO',' 戴尔（DELL）','佳能（Canon）','惠普（HP）','三星（SAMSUNG）']
          ],    
          [  
            ['/static/img/details/camera/camera1.jpg','尼康（Nikon） D3400 入门单反相机（AF-P DX 尼克尔 18','2899','113.74'],
            ['/static/img/details/camera/camera2.jpg','佳能（Canon）EOS 750D 单反套机 750D（18-55）套机','3979','156.11'],
            ['/static/img/details/camera/camera3.jpg','佳能（Canon） EOS 200D 单反套机 18-55mm套机 白色','3899','152.97'],
            ['/static/img/details/camera/camera4.jpg','佳能（Canon）PowerShot G7 X Mark II 数码相机 黑色','3999','156.90'],
            ['/static/img/details/camera/camera5.jpg','佳能（Canon）EOS 800D 单反套机 18-135mm套机','5999','235.36'],
            ['/static/img/details/camera/camera6.jpg','拍立得--富士 instax 趣奇Checky一次成像相机 mini25 白色','699','27.43'],
            ['/static/img/details/camera/camera7.jpg','索尼（SONY） ILCE-6000L微单套机 （16-50mm镜头 a6000）','3549','139.24'],
            ['/static/img/details/camera/camera8.jpg','富士（FUJIFILM）INSTAX 一次成像相机 MINI9相机 拍立得 烟','499','19.58'],
            ['/static/img/details/camera/camera9.jpg','尼康（Nikon） D5600 单反相机 18-140mm套机','5199','203.98'],
            ['/static/img/details/camera/camera10.jpg','Canon/佳能 入门级单反数码相机 EOS 1300D（EF-S 18）','3559','147.22'],
            ['/static/img/details/camera/camera11.jpg','佳能微单（Canon）EOS M50套机 微单相机 白色 M50配15-45','4209','167.90'],
            ['/static/img/details/camera/camera12.jpg','佳能（Canon）迷你单反EOS 200D（EF-S18-55mm f/4-5.6 IS','3999','157.15'],
            ['/static/img/details/camera/camera13.jpg','富士（FUJIFILM）INSTAX 一次成像相机 MINI9相机 拍立得','459','18.01'],
            ['/static/img/details/camera/camera14.jpg','索尼（SONY） ILCE-6300L APS-C旗舰微单单镜套机 （16-50mm ','5599','219.67'],
            ['/static/img/details/camera/camera15.jpg','富士（FUJIFILM）拍立得 趣奇（checky）instax mini90相机','1399','54.89'],
            ['/static/img/details/camera/camera16.jpg','索尼（SONY）Sonnar T* FE 55mm F1.8 ZA 蔡司全画幅标准','4699','184.36'],
            ['/static/img/details/camera/camera17.jpg','索尼（SONY） ILCE-6000L微单套机 （16-50mm镜头 a6000/','3528','138.42'],
            ['/static/img/details/camera/camera18.jpg','拍立得--富士（FUJIFILM） Instax mini90 拍立得相机 NEO ','1188','46.61'],
            ['/static/img/details/camera/camera19.jpg','佳能（Canon）EOS 80D 单反相机 18-135mm套机','8399','329.52'],
            ['/static/img/details/camera/camera20.jpg','佳能（Canon）EF 50mm f/1.8 STM 标准定焦镜头','699','27.43'],
            ['/static/img/details/camera/camera21.jpg','佳能微单（Canon）EOS M50套机 微单相机 黑色 M50配15-45','4209','167.90'],
            ['/static/img/details/camera/camera22.jpg','佳能（Canon）EOS M6 微单相机 银色 配EF15-45mm镜头','3709','153.01'],
            ['/static/img/details/camera/camera23.jpg','适马（SIGMA）ART 30mm F1.4 DC HSM 半画幅 大光圈标准定焦','1909','74.90'],
            ['/static/img/details/camera/camera24.jpg','索尼（SONY） ILCE-6000L微单套机 （16-50mm镜头 a6000','3499','137.28'],
            ['/static/img/details/camera/camera25.jpg','索尼（SONY） ILCE-6000L微单套机 （16-50mm镜头 a6000','3528','138.42'],
            ['/static/img/details/camera/camera26.jpg','尼康（Nikon） D5300 单反套机 18-140mm镜头套机','4400','172.63'],
            ['/static/img/details/camera/camera27.jpg','佳能 EOS 750D 单反套机 18-135mm套机','6199','243.21'],
            ['/static/img/details/camera/camera28.jpg','奥林巴斯（OLYMPUS）E-M10 MarkII-1442-EZ 微单电电动变焦','3899','152.97'],
            ['/static/img/details/camera/camera29.jpg','云腾（YUNTENG） VT-8008 微电影级专业大型三脚架云台套装','279','279'],
            ['/static/img/details/camera/camera30.jpg','索尼（SONY）ILCE-6500 微单数码相机APS-C画幅旗舰单机身 ','7499','294.21'],
            ['/static/img/details/camera/camera31.jpg','佳能（Canon） EOS 6D Mark II 单反相机 （24-105）STM套机','11999','470.76'],
            ['/static/img/details/camera/camera32.jpg','佳能（Canon） EOS 6D Mark II 单反相机 单机身','9499','372.68'],
            ['/static/img/details/camera/camera33.jpg','佳能 EOS 750D套机 入门级数码单反相机 佳能750D 港行18','5399','223.33'],
            ['/static/img/details/camera/camera34.jpg','佳能（Canon）EF 50mm f/1.8 STM 标准定焦镜头 EF 50mm','809','33.05'],
            ['/static/img/details/camera/camera35.jpg','理光（Ricoh）GR II WIFI\NFC\手机控制 超凡画质','4180','164'],
            ['/static/img/details/camera/camera36.jpg','索尼（SONY） DSC-RX100 M3/M4/M5黑卡数码相机 RX100','2050','80.43']
          ]
        ],
        [  
          [
            ['平板数码','全部','平板电脑','影音娱乐','电子教育','外设产品','电玩游戏','智能设备','手机配件'],        
            ['品牌：','全部','戴尔（DELL）','尼康（Nikon）','松下（Panasonic）','苹果（Apple）','HTC华为（HUAWEI）','小米（MI）',' 和冠（Wacom）','诺基亚（NOKIA）','华为（HUAWEI）']
          ],    
          [  
          
            ['/static/img/details/digital/digital1.jpg','苹果（Apple）AirPods无线耳机入耳式 蓝牙耳机 AirPods','1199','46.61'],
            ['/static/img/details/digital/digital2.jpg','苹果（Apple）2018年新款 iPad 平板电脑9.7英寸（A10芯片/支','3488','129.43'],
            ['/static/img/details/digital/digital3.jpg','苹果（Apple）2018年新款 iPad 平板电脑9.7英寸（A10芯片/支','3488','129.43'],
            ['/static/img/details/digital/digital4.jpg','苹果（Apple）2018年新款 iPad 平板电脑9.7英寸（A10芯片/支','3488','129.43'],
            ['/static/img/details/digital/digital5.jpg','小米（MI）AI音箱 小爱同学 人工语音智能网络音响 蓝牙wifi 低','349.9','14.48'],
            ['/static/img/details/digital/digital6.jpg','小米（MI）小米手环3 智能运动 心率监测 智能提醒 睡眠监测 计','199','6.64'],
            ['/static/img/details/digital/digital7.jpg','Beats X 蓝牙无线耳机 beatsx入耳式耳机 带麦可通话耳机 白色','937','36.77'],
            ['/static/img/details/digital/digital8.jpg','酷狗（KUGOU）小酷M1 无线运动蓝牙耳机 磁吸断电 雅黑色','119','4.67'],
            ['/static/img/details/digital/digital9.jpg','【京东配送】罗技（Logitech）G502 炫光自适应游戏鼠标 RGB鼠','399','14.87'],
            ['/static/img/details/digital/digital10.jpg','2018新款Apple Watch Series 4智能手表（GPS款金色/银色/深','3499','137.28'],
            ['/static/img/details/digital/digital11.jpg','品胜/Pisen插线板USB智能排插 KY-33 线长1.8米','99','2.71'],
            ['/static/img/details/digital/digital12.jpg','苹果（Apple）iPad Pro 平板电脑 10.5 英寸 2017款 玫瑰金色 64G ','5188','168.67'],
            ['/static/img/details/digital/digital13.jpg','罗马仕（ROMOSS）sense9 25000毫安 正品大容量充电宝 ','129','5.07'],
            ['/static/img/details/digital/digital14.jpg','苹果（Apple）iPad mini 4 平板电脑 WLAN版 金色 128G','2899','113.74'],
            ['/static/img/details/digital/digital15.jpg','苹果（Apple）Apple适用于10.5英寸iPad Pro的Smart Keyboard/Pencil 手写 P','788','30.92'],
            ['/static/img/details/digital/digital16.jpg','品胜（PISEN）20000毫安 移动电源/充电宝 双USB输出 液晶数','139','5.46'],
            ['/static/img/details/digital/digital17.jpg','苹果（Apple）iPad Pro 平板电脑 10.5 英寸 2017款 银色 256G','6388','215.31'],
            ['/static/img/details/digital/digital18.jpg','苹果（APPLE）原装耳机 Apple EarPods Lightning 接头的','228','12.52'],
            ['/static/img/details/digital/digital19.jpg','赛德斯（Sades）烽影机械键盘鼠标套装 游戏键鼠套装笔记本电','169','6.24'],
            ['/static/img/details/digital/digital20.jpg','索爱（soaiy）T1 真无线蓝牙耳机 商务入耳式 立体声 迷你运动','199','7.81'],
            ['/static/img/details/digital/digital21.jpg','苹果（Apple）iPad Pro 平板电脑 10.5 英寸 2017款 深空灰色','6388','231.01'],
            ['/static/img/details/digital/digital22.jpg','【京东配送】雷蛇（Razer）北海巨妖 游戏耳机 电竞耳麦 耳机','279','10.95'],
            ['/static/img/details/digital/digital23.jpg','罗马仕（ROMOSS） 超智能移动电源充电宝 20000毫安LCD显示','99','3.89'],
            ['/static/img/details/digital/digital24.jpg','2018年新款Apple Watch Series 4智能手表（GPS+蜂窝网络款','4299','168.67'],
            ['/static/img/details/digital/digital25.jpg','【任天堂+塞尔达券后价2589元，顺丰包邮，一年质保】','3289','127.78'],
            ['/static/img/details/digital/digital26.jpg','【TicWatch Pro旗舰版】智能手表男续航30天 成人wifi计步器','1499','50.97'],
            ['/static/img/details/digital/digital27.jpg','Beats Powerbeats3 by Dr. Dre Wireless 入耳式耳机 迷幻红','1468','57.60'],
            ['/static/img/details/digital/digital28.jpg','小米（MI）小米圈铁耳机 Pro 小米圈铁耳机 Pro','145','5.69'],
            ['/static/img/details/digital/digital29.jpg','罗马仕（ROMOSS）sense6 加量版超智能 移动电源/充电宝 ','89','3.50'],
            ['/static/img/details/digital/digital30.jpg','台电（Teclast） 乐存 U盘 32G 金属防水 CF32GBNCX','26.9','1.06'],
            ['/static/img/details/digital/digital31.jpg','小米(MI)移动电源2C 20000毫安 移动电源2/大容量充电宝 双USB','129','5.07'],
            ['/static/img/details/digital/digital32.jpg','独到DT-521锌合金苹果数据线iphone充电器线金属快速双面充','25','0.75'],
            ['/static/img/details/digital/digital33.jpg','Beats Beats Solo3 Wireless头戴式耳机无线蓝牙魔音b耳麦重低','1988','82.24'],
            ['/static/img/details/digital/digital34.jpg','小米（MI）小米移动电源2（10000mAh） 银色 10000毫安快充','79','3.10'],
            ['/static/img/details/digital/digital35.jpg','酷我（KUWO）K1 无线蓝牙运动耳机 磁吸断电 大振膜真低音 ','109','4.28'],
            ['/static/img/details/digital/digital36.jpg','skullcandy Smokin Buds 2骷髅头入耳式重低音耳机塞线控带麦','219','8.24']
          ]
        ],
        [
          [
            ['运动户外：','全部','运动休闲鞋','运动服饰','体育用品','骑行运动','游泳用品','户外装备','运动健康','运动包',
            '文体竞技','潮牌服饰','户外鞋服','户外包袋','垂钓用品','运动男鞋','运动女鞋','中性运动鞋','运动男装','运动女装','中性运动装','运动配件','童装童鞋'],
            ['品牌：','全部','CONVERSE 匡威','阿迪达斯（Adidas）','耐克（NIKE）','Dickies','New Balance NB','VEIL','北极绒']
          ],    
          [  
          
            ['/static/img/details/sports/sports1.jpg','阿迪达斯/三叶草男女鞋 SUPERSTAR情侣款经典金标贝','619','25.61'],
            ['/static/img/details/sports/sports2.jpg','PUMA彪马男鞋2018新款杨洋同款Suede Classic运动鞋舒适时尚','499','18.99'],
            ['/static/img/details/sports/sports3.jpg','Adidas阿迪达斯男鞋女鞋2018年新款SUPERSTR三叶草金标贝壳','659','26.44'],
            ['/static/img/details/sports/sports4.jpg','耐克男鞋NIKE 回到未来 奥利奥 经典潮鞋运动鞋休闲鞋板鞋','499','18.58'],
            ['/static/img/details/sports/sports5.jpg','匡威男鞋板鞋 ALL STAR 1970S三星黑标男女情侣低帮帆布鞋休','429','16.51'],
            ['/static/img/details/sports/sports6.jpg','Adidas阿迪达斯男裤2018秋季新款裤子运动裤透气时尚休闲裤收','219','8.24'],
            ['/static/img/details/sports/sports7.jpg','匡威男鞋女鞋all star 1970S 三星标经典款高帮运动休闲胶鞋帆布','559','22.30'],
            ['/static/img/details/sports/sports8.jpg','NIKE耐克男鞋 REVOLUTION 4 轻盈透气训练运动鞋休闲鞋缓震','399','14.44'],
            ['/static/img/details/sports/sports9.jpg','Adidas阿迪达斯三叶草男鞋女鞋 Superstar 经典金标贝壳头休闲','699','26.44'],
            ['/static/img/details/sports/sports10.jpg','CONVERSE 匡威男鞋女鞋All Star 常青款情侣经典低帮帆布鞋板鞋','289','10.68'],
            ['/static/img/details/sports/sports11.jpg','【支持微信支付】阿迪达斯adidas三叶草款金标贝壳头','619','25.61'],
            ['/static/img/details/sports/sports12.jpg','NIKE耐克男鞋 TESSEN 运动鞋透气时尚缓震耐磨训练鞋跑步鞋慢','499','18.58'],
            ['/static/img/details/sports/sports13.jpg','【支持微信支付】耐克Nike新款男鞋休闲鞋运动鞋运动休闲','549','22.71'],
            ['/static/img/details/sports/sports14.jpg','NIKE耐克男鞋 KYRIE FLYTRAP EP 欧文4代简版篮球鞋AJ1935','499','18.58'],
            ['/static/img/details/sports/sports15.jpg','Nike耐克短袖男上衣2018夏季新款针织透气运动休闲圆领速干短','169','5.34'],
            ['/static/img/details/sports/sports16.jpg','NIKE耐克男女鞋 奥利奥 减震轻便情侣跑步鞋板鞋网面运动休闲','429','16.51'],
            ['/static/img/details/sports/sports17.jpg','New Balance/NB男鞋 吴磊同款 574系列 复古鞋休闲鞋运动鞋 ','529','20.65'],
            ['/static/img/details/sports/sports18.jpg','【支持微信支付】彪马Puma男鞋春新款杨洋鹿晗同款耐磨低帮','449','18.58'],
            ['/static/img/details/sports/sports19.jpg','adidas阿迪达斯男鞋 alphabounce阿尔法系列 小椰子','679','26.44'],
            ['/static/img/details/sports/sports20.jpg','【支持微信支付】彪马Puma新款男女鞋板鞋运动鞋运动休闲','449','18.58'],
            ['/static/img/details/sports/sports21.jpg','阿迪达斯adidas新款男装卫衣外套运动服运动休闲S98803 黑/白 ','226','9.35'],
            ['/static/img/details/sports/sports22.jpg','adidas阿迪达斯男鞋 alphabounce阿尔法系列 小椰子','649','24.78'],
            ['/static/img/details/sports/sports23.jpg','NEW BALANCE/NB男鞋女鞋580系列复古跑步鞋运动休闲鞋','399','16.51'],
            ['/static/img/details/sports/sports24.jpg','Nike耐克男鞋 FLEX EXPERIENCE RN 7网面透气低帮运动休闲鞋轻','429','15.27'],
            ['/static/img/details/sports/sports25.jpg','Adidas阿迪达斯NEO男鞋 HOOPS 2.0新品运动鞋耐磨透气休闲鞋','399','16.51'],
            ['/static/img/details/sports/sports26.jpg','Adidas阿迪达斯男鞋女鞋2018秋季新款彭于晏同款ULTRABOOST','1099','45.46'],
            ['/static/img/details/sports/sports27.jpg','CONVERSE/匡威帽子男帽女帽经典款棒球帽鸭舌帽休闲运动遮阳','99','3.27'],
            ['/static/img/details/sports/sports28.jpg','Air Jordan 1 Mid AJ1 小黑红 洛杉矶 中帮 男女篮球鞋','1398','57.83'],
            ['/static/img/details/sports/sports29.jpg','耐克Nike Air Force 1 Mid 空军一号男子板鞋高低帮 315123-111 ','968','40.04'],
            ['/static/img/details/sports/sports30.jpg','adidas阿迪达斯男鞋 alphabounce阿尔法系列 小椰子','689','26.85'],
            ['/static/img/details/sports/sports31.jpg','NIKE/耐克男鞋 2018新款KWAZI小椰子 运动鞋潮流休闲鞋板鞋','469','18.58'],
            ['/static/img/details/sports/sports32.jpg','Nike耐克男鞋 Benassi黑白鸳鸯阴阳平底沙滩鞋 网红款 拖鞋凉鞋','229','8.24'],
            ['/static/img/details/sports/sports33.jpg','adidas阿迪达斯男鞋 经典人气 低帮轻便时尚板鞋运动小白鞋休闲','339','13.61'],
            ['/static/img/details/sports/sports34.jpg','NIKE/耐克男鞋 KOBE MENTALITY 科比曼巴精神3运动','499','17.75'],
            ['/static/img/details/sports/sports35.jpg','NIKE耐克男鞋 经典人气复刻低帮时尚板鞋休闲鞋舒适耐磨','429','16.51'],
            ['/static/img/details/sports/sports36.jpg','NIKE耐克女鞋 Roshe one花绳白勾 女神款 休闲鞋运动透气跑步','429','15.68']
          ]
        ],
        [  
          [
            ['服饰鞋靴','全部','男装','女装','男鞋','女鞋','内衣','服饰配件'],        
            ['品牌：','全部','马克华菲( FAIRWHALE)','lilbetter',' CollegeHome/克洛家','李维斯（Levis）','SIMWOOD/简木','杰克琼斯JackJones ','  阿玛尼（ARMANI）','幸福时光','mistletoe','花花公子（PLAYBOY）']
          ],         
          [      
            ['/static/img/details/clothes/clothes1.jpg','LINGWUZHE领舞者时尚休闲潮鞋男生舒适潮搭运动鞋气垫跑步','139','5.75'],
            ['/static/img/details/clothes/clothes2.jpg','LINGWUZHE领舞者秋季男运动鞋潮鞋都市运动高帮板鞋跑步鞋','109','4.51'],
            ['/static/img/details/clothes/clothes3.jpg','森马男鞋运动鞋男学生韩版百搭休闲鞋潮鞋子秋季男士运动休闲','269','11.13'],
            ['/static/img/details/clothes/clothes4.jpg','PRINT CITY男装2018新品潮牌工装裤男束脚小脚休闲裤 街头复','149','6.17'],
            ['/static/img/details/clothes/clothes5.jpg','【支持微信支付】OKKO男鞋2018新款白色高帮情侣鞋男韩版','128','5.30'],
            ['/static/img/details/clothes/clothes6.jpg','lilbetter牛仔裤男 2018夏季新款水洗九分裤时尚休闲小脚男士裤','178','7.37'],
            ['/static/img/details/clothes/clothes7.jpg','ERICD精选潮流复古百搭简约设计日系原创原宿风休闲裤男','119','4.93'],
            ['/static/img/details/clothes/clothes8.jpg','【五条装】俞兆林春夏新品男人船袜男袜短袜男棉袜短袜薄船袜','59','0.83'],
            ['/static/img/details/clothes/clothes9.jpg','【店铺每周上新】ERICD工装裤男大码潮流宽松弹力休闲裤男牛','109','4.51'],
            ['/static/img/details/clothes/clothes10.jpg','Septwolves/七匹狼男士内裤男平角裤莫代尔短裤四角裤青年性感','69','2.86'],
            ['/static/img/details/clothes/clothes11.jpg','森马男鞋运动鞋男学生韩版百搭休闲鞋潮鞋子秋季男士运动休闲','269','11.13'],
            ['/static/img/details/clothes/clothes12.jpg','lilbetter牛仔夹克男水洗渐变色上衣秋装外套宽松休闲男士外衣潮','238','9.85'],
            ['/static/img/details/clothes/clothes13.jpg','Collegehome 秋季时尚男士休闲裤男 潮牌个性系带宽松哈伦裤子','119','4.93'],
            ['/static/img/details/clothes/clothes14.jpg','【秋冬 3件套】1件卫衣+1件夹克+1条裤子 PRINTCITY复古休','429','17.75'],
            ['/static/img/details/clothes/clothes15.jpg','viishow2018秋季新款卫衣男 套头连帽男士外套 情侣装上衣韩版','169','6.29'],
            ['/static/img/details/clothes/clothes16.jpg','【微信支付 立返5元】mistletoe2018夏季新款男士休闲','89','3.69'],
            ['/static/img/details/clothes/clothes17.jpg','Lilbetter男士哈伦裤 小脚宽松束脚裤纯棉长裤bf风运动休闲裤男','168','6.95'],
            ['/static/img/details/clothes/clothes18.jpg','森马高帮板鞋男学生潮流2018新款韩版秋季百搭时尚休闲运动鞋','289','11.96'],
            ['/static/img/details/clothes/clothes19.jpg','俞兆林 男裤2018新款新款男士条纹休闲裤修身潮韩版百搭小脚','99','2.86'],
            ['/static/img/details/clothes/clothes20.jpg','【五条装】俞兆林男士船袜隐形舒适透气时尚百搭吸汗防臭跑步','59','1.24'],
            ['/static/img/details/clothes/clothes21.jpg','PRINT CITY 潮牌工装裤男2018秋季新品魔术贴收脚口小脚裤多','129','5.34'],
            ['/static/img/details/clothes/clothes22.jpg','College Home 韩版休闲连帽卫衣男宽松撞色拼接连帽卫衣后背字','99','4.10'],
            ['/static/img/details/clothes/clothes23.jpg','森马男鞋帆布鞋男高帮男潮鞋子秋季迷彩百搭学生韩版平底休闲','249','10.30'],
            ['/static/img/details/clothes/clothes24.jpg','Septwolves/七匹狼内裤男平角裤全棉吸汗透气青年四角裤青年棉','69','2.86'],
            ['/static/img/details/clothes/clothes25.jpg','【店铺每周上新】ERICD精选百搭潮流复古色系宽松掉肩ins港仔','119','4.93'],
            ['/static/img/details/clothes/clothes26.jpg','俞兆林2018新款秋冬季弹力小脚休闲直筒长裤子男韩版潮流牛仔','129','5.34'],
            ['/static/img/details/clothes/clothes27.jpg','【5折抢购】CH新款潮流短袖T恤衫学生休闲假两件日系韩版潮','59','2.03'],
            ['/static/img/details/clothes/clothes28.jpg','PRINT CITY 潮牌工装裤男束脚裤迷彩宽松嘻哈多口袋休闲裤男','109','4.51'],
            ['/static/img/details/clothes/clothes29.jpg','PRINT CITY 潮牌工装裤男2018秋季新品魔术贴收脚口小脚裤多','129','5.34'],
            ['/static/img/details/clothes/clothes30.jpg','Collegehome 秋季时尚男士休闲裤男 潮牌个性系带宽松哈伦裤子','119','4.93'],
            ['/static/img/details/clothes/clothes31.jpg','【灰色S/M预售9.30发】VIISHOW2018秋季新款卫衣男','169','6.29'],
            ['/static/img/details/clothes/clothes32.jpg','森马男鞋帆布鞋男高帮男潮鞋子秋季迷彩百搭学生韩版平底休闲','249','10.30'],
            ['/static/img/details/clothes/clothes33.jpg','ERICD精选潮流复古百搭简约设计日系原创原宿风休闲裤男','119','4.93'],
            ['/static/img/details/clothes/clothes34.jpg','衣品天成2018秋季新款男士休闲裤直筒修身潮流韩版情侣男装长','129.9','5.38'],
            ['/static/img/details/clothes/clothes35.jpg','黑色XXL3XL预售9.25日内发货 迷彩工装裤男日系潮牌宽松嘻哈','129','5.34'],
            ['/static/img/details/clothes/clothes36.jpg','【CB微信下单返现2元】秋装新品休闲男装 2018秋季新款ins衬','68','2.82']
          ]
        ],
        [  
          [
            ['箱包潮品','全部','潮流女包','精品男包','鲜花礼品','功能箱包','奢品配件','奢品鞋服'],        
            ['品牌：','全部','徕卡（Leica）','CASMELY','苹果（Apple）','vivo','DAKELE',' 蔻驰（COACH）','ALEXANDER','MCQUEEN','亚历山大·麦昆', 'By Creations(柏品)','Calvin Klein Jeans','Cote&Ciel']
          ],    
          [            
            ['/static/img/details/bag/bag1.jpg','库依娜 男双肩包男士商务背包旅行防雨百搭电脑书包女时尚潮流','139','4.10'],
            ['/static/img/details/bag/bag2.jpg','啄木鸟Plover头层牛皮女包时尚休闲单肩斜挎信封包迷你真皮手','229','9.48'],
            ['/static/img/details/bag/bag3.jpg','美洲野牛自动扣皮带男真皮韩版商务休闲青年腰带牛皮时尚裤腰','129','5.34'],
            ['/static/img/details/bag/bag4.jpg','OSDY2018新款个性男女韩版潮时尚百搭双肩包休闲电脑背包 黑','168','4.10'],
            ['/static/img/details/bag/bag5.jpg','库依娜 KUYINA 日系潮牌迷彩个性双肩包男生休闲旅行背包','159','4.10'],
            ['/static/img/details/bag/bag6.jpg','USO铝框行李箱女20寸拉杆箱万向轮24寸复古旅行箱金属硬箱子','398','16.47'],
            ['/static/img/details/bag/bag7.jpg','啄木鸟Plover链条小猪包小包包2018秋冬新款迷你复古单肩手提','199','8.24'],
            ['/static/img/details/bag/bag8.jpg','美洲野牛手拿包软皮真皮男包手抓包头层牛皮大容量男士手包钱','269','11.13'],
            ['/static/img/details/bag/bag9.jpg','阿尔皮纳袋鼠（L’ALPINA) 男士牛皮皮带时尚商务休闲型男自动','99','4.10'],
            ['/static/img/details/bag/bag10.jpg','乐菲尔女士钱包女长款牛皮拉链钱夹韩版菱格小香风黑色女式皮','59','2.45'],
            ['/static/img/details/bag/bag11.jpg','USO韩版拉杆箱万向轮24寸行李箱男女旅行箱万向轮密码登机皮','228','9.44'],
            ['/static/img/details/bag/bag12.jpg','乐菲尔新品女士钱包女长款韩版牛皮拉链大钞夹油蜡皮手抓钱包','89','3.69'],
            ['/static/img/details/bag/bag13.jpg','库依娜 KUYINA 休闲男士双肩包韩版高中学生书包时尚潮流皮质','148','6.13'],
            ['/static/img/details/bag/bag14.jpg','lefeel乐菲尔2018新款斜挎包女小包单肩包女手提包菱格链条包','135','5.59'],
            ['/static/img/details/bag/bag15.jpg','美洲野牛 皮带男腰带真皮带自动扣腰带牛皮腰带商务裤带鳄鱼纹','159','4.10'],
            ['/static/img/details/bag/bag16.jpg','lefeel乐菲尔时尚包包2018新款女包小包斜挎包单肩包绒面磨砂','149','6.17'],
            ['/static/img/details/bag/bag17.jpg','美洲野牛男士真皮自动扣皮带礼盒扣头套装节日生日礼物送男友','188','7.78'],
            ['/static/img/details/bag/bag18.jpg','【男人四件套】美洲野牛双肩包钱包腰带男商务电脑包大容量旅','399','16.51'],
            ['/static/img/details/bag/bag19.jpg','库依娜 KUYINA 新款潮男简约双肩包韩版皮质英伦商务潮流背包','159','4.10'],
            ['/static/img/details/bag/bag20.jpg','纽芝兰2017新款韩版手提包百搭单肩女包包铆钉斜挎包小方包','239','9.89'],
            ['/static/img/details/bag/bag21.jpg','lefeel/乐菲尔个性小香风菱格链条包包2018新款女包单肩手提简','148','6.13'],
            ['/static/img/details/bag/bag22.jpg','库依娜 KUYINA男装双肩包男士软皮包土旅行商务男包背包青年','188','4.10'],
            ['/static/img/details/bag/bag23.jpg','啄木鸟Plover明星同款迷你链条包包女2018新款时尚斜挎百搭单','299','12.37'],
            ['/static/img/details/bag/bag24.jpg','库依娜 男包手提包大容量男士背包休闲单肩包斜跨包潮流男士手','168','6.95'],
            ['/static/img/details/bag/bag25.jpg','LALPINA/阿尔皮纳袋鼠(意大利)小钱包女短款2018新款时尚印花','159','6.58'],
            ['/static/img/details/bag/bag26.jpg','LALPINA/阿尔皮纳袋鼠(意大利)2018新款男士皮带真皮商务','129','5.34'],
            ['/static/img/details/bag/bag27.jpg','OSDY拉杆箱万向轮20/24寸行李箱26/29寸旅行箱男女登机箱 24','288','10.68'],
            ['/static/img/details/bag/bag28.jpg','OSDY拉杆箱20/22寸商务登机箱男旅行箱万向轮24/26寸行李箱','498','6.47'],
            ['/static/img/details/bag/bag29.jpg','七匹狼 男士皮带自动扣百搭商务休闲腰带 WA20001J 黑色','49','2.03'],
            ['/static/img/details/bag/bag30.jpg','库依娜/KUYINA双肩包男女情侣防盗笔记本电脑包双肩书包男女','188','4.10'],
            ['/static/img/details/bag/bag31.jpg','七匹狼钱包男长款 头层牛皮青年日韩商务钱夹 男士皮夹真皮软长','229','9.48'],
            ['/static/img/details/bag/bag32.jpg','库依娜 吃鸡战术绝地求生三级背包学生电脑书包防水迷彩usb单','129','5.34'],
            ['/static/img/details/bag/bag33.jpg','库依娜 KUYINA 2018新款男士牛津布USB充电耳机防盗胸包时尚','119','4.10'],
            ['/static/img/details/bag/bag34.jpg','OSDY拉杆箱万向轮20/24寸行李箱26/29寸旅行箱男女登机箱 26','308','11.92'],
            ['/static/img/details/bag/bag35.jpg','木村耀司双肩包韩版简约旅行背包电脑休闲男包初中高中学生书','99','4.10'],
            ['/static/img/details/bag/bag36.jpg','美洲野牛男士真皮自动扣皮带礼盒扣头套装节日生日礼物送男友','188','7.78']
          ]
        ],
        [  
          [
            ['美妆护肤','全部','面部护肤','时尚彩妆','经典香氛','美容/发工具','男士专区'],        
            ['品牌：','全部','KATA','A.H.C','Bliss Spas/必列斯','Cle De Peau(柯丽柏蒂)',' Decleor/思妍丽','Eve Lom',' Jane Iredale/珍爱芮德','La Prairie(蓓莉)','Lancaster/兰嘉丝汀','Laura Mercier/罗拉玛斯亚']
          ],        
          [       
           
          
            ['/static/img/details/skin/skin1.jpg','【专柜正品】MAC/魅可口红 子弹头口红 chili小辣椒秀智 3g chili','169','6.13'],
            ['/static/img/details/skin/skin2.jpg','欧莱雅男士火山岩洗面奶水凝露套装控油清痘清爽补水保湿无油','210','4.51'],
            ['/static/img/details/skin/skin3.jpg','【香港直邮】Dior/迪奥 女士香水Q版5ml套装系列 真我5ml花漾','125','4.10'],
            ['/static/img/details/skin/skin4.jpg','【香港直邮】 Dior/迪奥 烈艳蓝金系列 烈焰蓝金999滋润款 口红','339','11.79'],
            ['/static/img/details/skin/skin5.jpg','膜法世家黑+白瓷娃娃BB肌面膜贴套装20片 补水亮肤 嫩滑细致','188','3.27'],
            ['/static/img/details/skin/skin6.jpg','欣兰（D.M.C）黑里透白冻膜清洁面膜 225g','149','6.17'],
            ['/static/img/details/skin/skin7.jpg','Venes marble 12色大理石眼影盘 网红眼影不飞粉 12色大理石眼','179','5.75'],
            ['/static/img/details/skin/skin8.jpg','百雀羚PECHOIN 小雀幸静润补水保湿面膜 草本滋润精华海藻蚕','89','3.27'],
            ['/static/img/details/skin/skin9.jpg','【海外直邮】MAC/魅可 子弹头唇膏 Chili小辣椒Ruby Woo哑光','178','6.54'],
            ['/static/img/details/skin/skin10.jpg','【正品保障 闪电发货】膜法世家玻尿酸补水保湿面膜贴25ml*10','59.9','1.20'],
            ['/static/img/details/skin/skin11.jpg','【海外直邮】Dr.Jart+/蒂佳婷药丸面膜蓝色 绿色款 补水美白面','168','6.95'],
            ['/static/img/details/skin/skin12.jpg','【海外直邮】Armani/阿玛尼 红管 臻致丝绒哑光唇釉 保湿豆沙','388','14.81'],
            ['/static/img/details/skin/skin13.jpg','城野医生（Dr.Ci.Labo）去黑头粉刺收缩毛孔化妆水','139','5.75'],
            ['/static/img/details/skin/skin14.jpg','【保税区直发 正品保障】 法国BIODERMA贝德玛舒妍洁肤卸妆','135','5.59'],
            ['/static/img/details/skin/skin15.jpg','【海外直邮】美国EltaMD温和保湿洗面奶氨基酸泡沫洁面乳男女','175','7.24'],
            ['/static/img/details/skin/skin16.jpg','【海外直邮】Freeplus/芙丽芳丝深层清洁洗面奶100g 氨基酸洗','128','5.30'],
            ['/static/img/details/skin/skin17.jpg','【海外直邮】Dior/迪奥 烈焰蓝金系列唇膏 双色夹心','315','13.03'],
            ['/static/img/details/skin/skin18.jpg','【海外直邮】Givenchy/纪梵希四宫格轻盈无痕明星散粉蜜粉','419','17.34'],
            ['/static/img/details/skin/skin19.jpg','【香港直邮】正品授权 RAY 泰国（妆蕾版）蚕丝补水保湿面膜','119','4.93'],
            ['/static/img/details/skin/skin20.jpg','【香港直邮】Chanel/香奈儿 炫亮魅力丝绒口红 3.5g 限量色号','400','13.16'],
            ['/static/img/details/skin/skin21.jpg','【专柜正品】papa recipe春雨 蜂胶补水 滋润修护 清洁保湿 面膜','99','4.10'],
            ['/static/img/details/skin/skin22.jpg','膜法世家水嫩亮采三合一气垫凝水面膜贴套盒21片补水保湿亮肤','129','2.86'],
            ['/static/img/details/skin/skin23.jpg','泰国安娜贝拉Annabella海藻面膜补水嫩白10片/盒 2盒装','129','5.34'],
            ['/static/img/details/skin/skin24.jpg','【海外直邮】ISHIZAWA LABS/石泽研究所 毛穴抚子大米面膜','118','4.89'],
            ['/static/img/details/skin/skin25.jpg','兰芝（LANEIGE）雪纱丝柔修颜隔离霜 提亮肤色 30ml 最新版','229','7.82'],
            ['/static/img/details/skin/skin26.jpg','【海外直邮】YSL/圣罗兰黑管唇釉5.5ml 持久保湿滋润口红正品','319','12.33'],
            ['/static/img/details/skin/skin27.jpg','【海外直邮】Dior/迪奥 烈焰蓝金系列唇膏 双色夹心','315','13.03'],
            ['/static/img/details/skin/skin28.jpg','膜法世家男士吸黑*控油多效面膜贴7片收缩毛孔补水亮肤','59','2.45'],
            ['/static/img/details/skin/skin29.jpg','一叶子白百合提亮补水五件礼盒 补水 滋润 美白 保湿【下单送护','199','7.82'],
            ['/static/img/details/skin/skin30.jpg','送喷雾 FOREO LUNA mini2 第二代 露娜家用洁面仪 粉红色 硅胶','1280','45.46'],
            ['/static/img/details/skin/skin31.jpg','韩国AHC第7代眼霜 滋润紧致保湿淡化细纹改善黑眼圈全脸眼霜','99','3.52'],
            ['/static/img/details/skin/skin32.jpg','【海外直邮】A.by bom超能婴儿冰凝修复保湿补水美白面膜：桃','120','4.97'],
            ['/static/img/details/skin/skin33.jpg','香港直邮 雅诗兰黛Estee lauder DW持久持妆粉底液 30ML 17号','385','14.69'],
            ['/static/img/details/skin/skin34.jpg','【专柜正品】Armani/阿玛尼 红管丝绒哑光唇釉 6.5ml #405稀','358','13.99'],
            ['/static/img/details/skin/skin35.jpg','【专柜正品】YSL/圣罗兰 莹亮纯魅圆管唇膏 4.5g 12红粉派对/珊','315','11.79'],
            ['/static/img/details/skin/skin36.jpg','泰国ray蚕丝面膜金色10片+银色10片 金色10片+银色10片','129','5.34']
          ]
        ],
        [  
          [
            ['家电家居','全部','电视影音','厨房小电','生活电器','个护健康','家居家纺','厨卫大电','空调','冰箱洗衣机'],        
            ['品牌：','全部','苹果（Apple）',' 小米（MI）','HTC','诺基亚（NOKIA）','华为（HUAWEI）','OPPO',' 戴尔（DELL）','佳能（Canon）','惠普（HP）','三星（SAMSUNG）']
          ],    
          [                 
          
            ['/static/img/details/electrical/electrical1.jpg','【京东配送】飞科(FLYCO)智能电动剃须刀 全身水洗刮胡 宝石','149','5.85'],
            ['/static/img/details/electrical/electrical2.jpg','【京东配送】九阳（Joyoung）电饭煲4L电饭锅智能预约JYF','179','6.24'],
            ['/static/img/details/electrical/electrical3.jpg','【京东配送】小米（MI）电视 50英寸 4K 智能WiFi网络平板','2199','86.28'],
            ['/static/img/details/electrical/electrical4.jpg','【京东配送】美的（Midea）料理机 多功能榨汁机 家用搅拌机','89','3.34'],
            ['/static/img/details/electrical/electrical5.jpg','【京东配送】德尔玛（Deerma）加湿器 4L大容量','69.9','2.75'],
            ['/static/img/details/electrical/electrical6.jpg','【京东配送】九阳（Joyoung）电磁炉 21HEC05经典款 赠汤锅','179','7.03'],
            ['/static/img/details/electrical/electrical7.jpg','【爆品热销】TCL 5.5公斤 全自动波轮洗衣机 一键脱水','729','27.43'],
            ['/static/img/details/electrical/electrical8.jpg','【京东配送】飞利浦（PHILIPS）SPS3421C/93 插排','29.8','1.17'],
            ['/static/img/details/electrical/electrical9.jpg','米家 （MIJIA ）小米声波电动牙刷成人充电式 智能电动牙刷','199','7.42'],
            ['/static/img/details/electrical/electrical10.jpg','乐视 原装 黑色 蓝牙运动耳机 8小时续航电量专业运动调音 运动','79','3.27'],
            ['/static/img/details/electrical/electrical11.jpg','【京东配送】TCL 6公斤 全自动波轮洗衣机 一键脱水 10种洗涤','799','28.61'],
            ['/static/img/details/electrical/electrical12.jpg','飞利浦剃须刀电动刮胡刀充电式男士胡须刀三头全身水洗正品','329','13.61'],
            ['/static/img/details/electrical/electrical13.jpg','京东叮咚(DingDong)mini2 迷你音响 /WIFI智能音箱低音炮 AI家','299','3.89'],
            ['/static/img/details/electrical/electrical14.jpg','【货源稀缺+抓紧抢购】小米电视4A L32M5-AZ 32英寸','949','34.49'],
            ['/static/img/details/electrical/electrical15.jpg','飞科(FLYCO)FS372全身水洗电动剃须刀 紫色 FS372 个护健康','199','7.81'],
            ['/static/img/details/electrical/electrical16.jpg','飞利浦剃须刀电动三头胡须刀男士充电式刮胡刀S5091正品全身','599','23.51'],
            ['/static/img/details/electrical/electrical17.jpg','【京东配送】荣事达（Royalstar）DZG15H 多功能双','49','1.93'],
            ['/static/img/details/electrical/electrical18.jpg','现代/HYUNDAI 迷你单桶洗衣机 XPB45-298 4.5公斤半自动波轮','299','12.37'],
            ['/static/img/details/electrical/electrical19.jpg','Usmile Y1 声波电动牙刷 防水耐用 刷牙更干净 蜜粉','289','11.96'],
            ['/static/img/details/electrical/electrical20.jpg','【京东配送】飞科(FLYCO)FH6651可折叠电吹风机','79','3.10'],
            ['/static/img/details/electrical/electrical21.jpg','【京东配送】康夫（Kangfu）电吹风机家用 KF-5843 大功率','59','2.32'],
            ['/static/img/details/electrical/electrical22.jpg','飞科（FLYCO）FS711 电动剃须刀男士刮胡刀充电式胡须刀 黑','49','1.93'],
            ['/static/img/details/electrical/electrical23.jpg','米家（MIJIA）小米生态链LED写字灯 阅读台灯智能台灯 任意调','159','6.24'],
            ['/static/img/details/electrical/electrical24.jpg','【京东配送】九阳（Joyoung）榨汁机 双杯 快速料理 可搅拌碎','94','3.69'],
            ['/static/img/details/electrical/electrical25.jpg','飞利浦剃须刀电动充电式YQ6008旋转式三刀头男士胡须','239','9.38'],
            ['/static/img/details/electrical/electrical26.jpg','美的（Midea）电水壶1.7L 304不锈钢电热水壶 双层防烫保温烧','99','3.73'],
            ['/static/img/details/electrical/electrical27.jpg','【京东配送】戴森(Dyson) 吹风机 Dyson Supersonic 电吹风','2990','111.43'],
            ['/static/img/details/electrical/electrical28.jpg','【京东配送】TCL 7公斤 全自动波轮洗衣机 一键脱水','879','34.49'],
            ['/static/img/details/electrical/electrical29.jpg','飞利浦（PHILIPS）剃须刀 充电式电动刮胡刀 荷兰原装进口刀头','129','5.34'],
            ['/static/img/details/electrical/electrical30.jpg','飞利浦电动剃须刀充电式男刮胡刀三刀头干湿两用S5082礼盒装','599','24.78'],
            ['/static/img/details/electrical/electrical31.jpg','康佳（KONKA）电热水壶 304不锈钢 双层防烫烧水壶','49','1.93'],
            ['/static/img/details/electrical/electrical32.jpg','【京东配送】超人(SID) SA7135 充电式电动剃须刀 刮胡刀 三刀','79','3.10'],
            ['/static/img/details/electrical/electrical33.jpg','美的（Midea）电磁炉整版触摸式WK2102T(赠汤锅+炒锅）','179','7.03'],
            ['/static/img/details/electrical/electrical34.jpg','【京东配送】TCL 118升 小型双门电冰箱 LED照明 迷你节能','879','31.35'],
            ['/static/img/details/electrical/electrical35.jpg','【张梓琳同款】飞利浦声波震动钻石亮白电动牙刷','1099','43.12'],
            ['/static/img/details/electrical/electrical36.jpg','【张梓琳同款】飞利浦声波震动钻石亮白电动牙刷','1099','45.46']
          ]
        ]
      ],
      txt:null
    }
  },
  methods: {
    goto(index){
      this.txt = this.details[index];
    }
  },
  mounted(){
    this.txt = this.details[this.$route.params.listid];
  }

}
</script>
  
<style scoped>
.detail{width: 1220px;height:480px;margin:0 auto;color: #fff;position: relative; background: #fff;}
</style>
  