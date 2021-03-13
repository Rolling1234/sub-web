<template>
  <div>
    <el-row style="margin-top: 10px">
      <el-col>
        <el-card>
          <div slot="header">
            订阅转换
            <svg-icon
              icon-class="github"
              style="margin-left: 10px"
              @click="goToProject"
            />
            <svg-icon
              icon-class="telegram"
              style="margin-left: 10px"
              @click="gotoTgChannel"
            />
            <!--<div style="float: right; margin-top: -10px">
              <a
                href="https://space.bilibili.com/138129883"
                target="_blank"
                style="text-decoration: none; color: #ffffff; margin-left: 20px"
                ><svg
                  t="1614753109467"
                  class="icon"
                  viewBox="0 0 2241 1024"
                  version="1.1"
                  xmlns="http://www.w3.org/2000/svg"
                  p-id="6328"
                  width="40"
                  height="40"
                >
                  <path
                    d="M626.875127 734.992893c-32.227411-24.430457-68.613198-41.583756-106.038579-56.657868-76.410152-30.148223-156.458883-41.063959-238.067005-38.984772-19.232487 0-38.464975 1.559391-58.217259 2.598985 0-1.559391-1.559391-3.638579-1.559391-6.237563-5.19797-58.217259-11.435533-116.434518-15.593909-173.612183-3.638579-47.82132-5.19797-95.64264-6.237563-143.463959-1.559391-92.004061-1.559391-183.488325-1.559391-275.492386 0-21.831472-1.559391-19.232487-18.192893-11.95533-51.459898 20.791878-102.4 41.063959-153.859898 60.816244C25.989848 93.563452 23.390863 98.761421 24.430457 101.360406c15.593909 58.217259 27.029442 117.993909 34.826396 177.250761 7.796954 51.459898 14.554315 101.360406 21.831472 151.780711 6.237563 44.182741 10.395939 88.365482 15.593909 133.06802 5.19797 45.222335 11.435533 90.44467 16.633503 136.186802 5.19797 43.662944 10.395939 85.766497 15.593909 129.429442 3.638579 31.187817 6.75736 61.855838 9.356345 93.043655 1.559391 24.430457 3.638579 48.860914 4.158376 72.251777 0 5.19797 1.559391 7.796954 6.75736 7.796954 11.435533 0 21.831472 1.559391 32.747208 0 53.019289-5.19797 106.038579-8.836548 158.018274-16.633503 40.024365-6.237563 79.009137-15.593909 117.474112-28.588832 54.57868-18.192893 101.360406-49.380711 146.582741-85.246701 19.232487-14.554315 34.826396-32.227411 41.583756-54.57868C660.142132 780.215228 653.904569 755.264975 626.875127 734.992893L626.875127 734.992893zM327.472081 908.085279c-7.796954-58.217259-15.593909-114.875127-23.390863-171.013198 30.148223 6.75736 156.97868 57.177665 163.216244 64.974619C421.035533 836.873096 375.293401 872.219289 327.472081 908.085279L327.472081 908.085279zM932.515736 763.061929c-2.598985-30.148223-5.19797-61.855838-8.836548-92.004061-3.638579-41.583756-7.796954-83.167513-11.435533-125.271066-3.638579-38.464975-5.19797-76.410152-7.796954-114.875127-3.638579-53.019289-7.796954-106.038579-11.435533-159.057868l-7.796954-117.474112c-1.039594-14.554315-6.75736-18.192893-21.831472-17.153299-18.192893 1.559391-35.86599 2.598985-54.058883 3.638579-15.593909 1.559391-31.187817 3.638579-46.261929 5.19797 46.781726 248.462944 67.573604 497.445685 92.004061 744.349239 28.588832 2.598985 54.57868 4.158376 81.608122 6.75736 5.19797 1.039594 7.796954 0 7.796954-5.19797l-2.598985-28.588832C939.792893 829.076142 936.154315 795.809137 932.515736 763.061929L932.515736 763.061929zM790.091371 794.249746c-3.638579-31.187817-6.75736-61.855838-10.395939-93.043655-3.638579-35.346193-6.75736-71.212183-11.435533-106.558376-2.598985-21.831472-6.237563-42.62335-9.356345-63.415228-1.039594-7.796954-6.237563-11.435533-14.554315-10.395939-14.554315 1.559391-30.148223 1.559391-45.222335 3.638579-20.791878 2.598985-41.583756 6.237563-63.415228 8.836548 25.989848 135.667005 51.979695 268.215228 79.009137 402.84264 31.187817-4.158376 60.816244-7.796954 90.964467-11.435533-1.039594-10.395939-2.598985-20.791878-3.638579-30.148223C797.888325 860.263959 793.729949 826.996954 790.091371 794.249746L790.091371 794.249746zM1100.929949 933.035533c-1.039594-51.459898-2.598985-101.360406-3.638579-152.820305-1.039594-63.415228 0-127.870051 0-191.285279 0-14.034518-1.039594-27.029442-1.559391-41.063959 0-6.237563-3.638579-11.435533-10.395939-11.435533-27.029442-1.039594-54.57868-1.559391-81.608122-1.559391-10.395939 0-19.752284 1.559391-30.148223 3.638579 1.039594 3.638579 1.039594 6.237563 1.039594 8.836548 3.638579 43.662944 7.796954 86.806091 11.435533 129.429442 3.638579 41.583756 7.796954 84.207107 11.435533 125.790863 4.158376 45.222335 7.796954 90.44467 11.95533 135.667005 0 2.598985 4.158376 6.75736 6.75736 6.75736 27.549239 1.039594 56.657868 0 85.766497 0C1100.929949 939.273096 1100.929949 935.634518 1100.929949 933.035533L1100.929949 933.035533zM750.067005 470.936041c-5.19797-49.380711-9.356345-96.162437-14.034518-143.983756-1.039594-6.237563-3.638579-9.356345-8.836548-9.356345-16.633503 0-33.786802 0-51.459898 1.039594 6.75736 53.019289 12.994924 103.959391 19.752284 156.458883C714.720812 473.535025 731.874112 473.015228 750.067005 470.936041L750.067005 470.936041zM1093.132995 478.732995 1093.132995 346.704569c0-9.356345-3.638579-11.95533-11.435533-11.95533l-45.222335 0 0 151.780711c19.752284 1.039594 38.464975 1.559391 56.657868 2.598985L1093.132995 478.732995 1093.132995 478.732995zM673.656853 477.173604l0-10.395939c-2.598985-27.029442-6.237563-53.019289-8.836548-80.048731-1.559391-17.153299-3.638579-33.786802-5.19797-51.459898-1.039594-4.158376 1.039594-10.395939-6.237563-9.356345-16.633503 1.559391-32.747208 5.19797-49.380711 6.75736 9.356345 51.459898 18.192893 101.360406 27.549239 151.780711L673.656853 477.173604 673.656853 477.173604zM1017.762437 486.010152 1017.762437 407.001015c0-20.791878-1.039594-42.62335 0-63.415228 0-7.796954-2.598985-9.356345-9.356345-9.356345l-46.261929 0c4.158376 54.058883 7.796954 104.998985 11.95533 155.419289C988.13401 488.609137 1002.168528 487.569543 1017.762437 486.010152L1017.762437 486.010152zM1017.762437 486.010152"
                    fill="#FB7299"
                    p-id="6329"
                  ></path>
                  <path
                    d="M1728.84467 734.992893c-32.227411-24.430457-68.613198-41.583756-106.038579-56.657868-76.410152-30.148223-156.458883-41.063959-238.067005-38.984772-19.232487 0-38.464975 1.559391-58.217259 2.598985 0-1.559391-1.559391-3.638579-1.559391-6.237563-5.19797-58.217259-11.435533-116.434518-15.593909-173.612183-3.638579-47.82132-5.19797-95.64264-6.237563-143.463959-1.559391-92.004061-1.559391-183.488325-1.559391-275.492386 0-21.831472-1.559391-19.232487-18.192893-11.95533-51.459898 20.791878-102.4 41.063959-153.859898 60.816244-1.559391 1.039594-4.158376 6.237563-3.638579 8.836548 15.593909 58.217259 27.029442 117.993909 34.826396 177.250761 7.796954 51.459898 14.554315 101.360406 21.831472 151.780711 6.237563 44.182741 10.395939 88.365482 15.593909 133.06802 5.19797 45.222335 11.435533 90.44467 16.633503 136.186802 5.19797 43.662944 10.395939 85.766497 15.593909 129.429442 3.638579 31.187817 6.75736 61.855838 9.356345 93.043655 1.559391 24.430457 3.638579 48.860914 4.158376 72.251777 0 5.19797 1.559391 7.796954 6.75736 7.796954 11.435533 0 21.831472 1.559391 32.747208 0 53.019289-5.19797 106.038579-8.836548 158.018274-16.633503 40.024365-6.237563 79.009137-15.593909 117.474112-28.588832 54.57868-18.192893 101.360406-49.380711 146.582741-85.246701 19.232487-14.554315 34.826396-32.227411 41.583756-54.57868C1762.111675 780.215228 1755.874112 755.264975 1728.84467 734.992893L1728.84467 734.992893zM1429.441624 908.085279c-7.796954-58.217259-15.593909-114.875127-23.390863-171.013198 30.148223 6.75736 156.97868 57.177665 163.216244 64.974619C1523.005076 836.873096 1477.262944 872.219289 1429.441624 908.085279L1429.441624 908.085279zM2034.485279 763.061929c-2.598985-30.148223-5.19797-61.855838-8.836548-92.004061-3.638579-41.583756-7.796954-83.167513-11.435533-125.271066-3.638579-38.464975-5.19797-76.410152-7.796954-114.875127-3.638579-53.019289-7.796954-106.038579-11.435533-159.057868l-7.796954-117.474112c-1.039594-14.554315-6.75736-18.192893-21.831472-17.153299-18.192893 1.559391-35.86599 2.598985-54.058883 3.638579-15.593909 1.559391-31.187817 3.638579-46.261929 5.19797 46.781726 248.462944 67.573604 497.445685 92.004061 744.349239 28.588832 2.598985 54.57868 4.158376 81.608122 6.75736 5.19797 1.039594 7.796954 0 7.796954-5.19797l-2.598985-28.588832C2041.762437 829.076142 2038.123858 795.809137 2034.485279 763.061929L2034.485279 763.061929zM1892.060914 794.249746c-3.638579-31.187817-6.75736-61.855838-10.395939-93.043655-3.638579-35.346193-6.75736-71.212183-11.435533-106.558376-2.598985-21.831472-6.237563-42.62335-9.356345-63.415228-1.039594-7.796954-6.237563-11.435533-14.554315-10.395939-14.554315 1.559391-30.148223 1.559391-45.222335 3.638579-20.791878 2.598985-41.583756 6.237563-63.415228 8.836548 25.989848 135.667005 51.979695 268.215228 79.009137 402.84264 31.187817-4.158376 60.816244-7.796954 90.964467-11.435533-1.039594-10.395939-2.598985-20.791878-3.638579-30.148223C1899.857868 860.263959 1895.699492 826.996954 1892.060914 794.249746L1892.060914 794.249746zM2202.899492 933.035533c-1.039594-51.459898-2.598985-101.360406-3.638579-152.820305-1.039594-63.415228 0-127.870051 0-191.285279 0-14.034518-1.039594-27.029442-1.559391-41.063959 0-6.237563-3.638579-11.435533-10.395939-11.435533-27.029442-1.039594-54.57868-1.559391-81.608122-1.559391-10.395939 0-19.752284 1.559391-30.148223 3.638579 1.039594 3.638579 1.039594 6.237563 1.039594 8.836548 3.638579 43.662944 7.796954 86.806091 11.435533 129.429442 3.638579 41.583756 7.796954 84.207107 11.435533 125.790863 4.158376 45.222335 7.796954 90.44467 11.95533 135.667005 0 2.598985 4.158376 6.75736 6.75736 6.75736 27.549239 1.039594 56.657868 0 85.766497 0C2202.899492 939.273096 2202.899492 935.634518 2202.899492 933.035533L2202.899492 933.035533zM1852.036548 470.936041c-5.19797-49.380711-9.356345-96.162437-14.034518-143.983756-1.039594-6.237563-3.638579-9.356345-8.836548-9.356345-16.633503 0-33.786802 0-51.459898 1.039594 6.75736 53.019289 12.994924 103.959391 19.752284 156.458883C1816.690355 473.535025 1833.843655 473.015228 1852.036548 470.936041L1852.036548 470.936041zM2195.102538 478.732995 2195.102538 346.704569c0-9.356345-3.638579-11.95533-11.435533-11.95533l-45.222335 0 0 151.780711c19.752284 1.039594 38.464975 1.559391 56.657868 2.598985L2195.102538 478.732995 2195.102538 478.732995zM1775.626396 477.173604l0-10.395939c-2.598985-27.029442-6.237563-53.019289-8.836548-80.048731-1.559391-17.153299-3.638579-33.786802-5.19797-51.459898-1.039594-4.158376 1.039594-10.395939-6.237563-9.356345-16.633503 1.559391-32.747208 5.19797-49.380711 6.75736 9.356345 51.459898 18.192893 101.360406 27.549239 151.780711L1775.626396 477.173604 1775.626396 477.173604zM2119.73198 486.010152 2119.73198 407.001015c0-20.791878-1.039594-42.62335 0-63.415228 0-7.796954-2.598985-9.356345-9.356345-9.356345l-46.261929 0c4.158376 54.058883 7.796954 104.998985 11.95533 155.419289C2090.103553 488.609137 2104.138071 487.569543 2119.73198 486.010152L2119.73198 486.010152zM2119.73198 486.010152"
                    fill="#FB7299"
                    p-id="6330"
                  ></path></svg
              ></a>
            </div>
            <div style="float: right; margin-top: -10px">
              <a
                href="https://youtube.com/channel/UCKHJ2UPlkNsDRj1cVXi0UsA"
                target="_blank"
                style="text-decoration: none; color: #ffffff; margin-left: 20px"
                ><svg
                  t="1614752844897"
                  class="icon"
                  viewBox="0 0 2453 1024"
                  version="1.1"
                  xmlns="http://www.w3.org/2000/svg"
                  p-id="3565"
                  width="40"
                  height="40"
                >
                  <path
                    d="M2437.368875 220.776166s-14.450804-100.352803-58.204626-144.508036C2323.769502 18.464916 2261.149353 18.063505 2232.649157 14.852215 2028.330851 0 1721.652685 0 1721.652685 0h-0.802822s-306.678165 0-511.397883 14.852215c-28.500196 3.21129-90.718934 3.612701-146.515093 61.817326-43.753822 44.155233-58.204626 144.508036-58.204625 144.508036s-14.450804 117.613485-14.450804 235.628381v110.388084c0 117.613485 14.450804 235.628381 14.450804 235.628381s14.450804 100.352803 58.204625 144.508036c55.394747 57.803214 128.451588 56.19757 160.965896 62.218737 116.810662 11.239514 496.94708 14.450804 496.94708 14.450804s307.079577-0.401411 511.397883-15.253626c28.500196-3.21129 90.718934-3.612701 146.515092-61.817327 43.753822-44.155233 58.204626-144.508036 58.204626-144.508036s14.450804-117.613485 14.450803-235.628381v-110.388083c0.401411-118.014896-14.049392-235.628381-14.049392-235.628381"
                    fill="#D54029"
                    p-id="3566"
                  ></path>
                  <path
                    d="M915.217562 828.111329h-93.127401v-53.789102C786.765974 814.864759 757.061544 834.935319 724.547236 834.935319c-28.500196 0-48.570757-13.647981-58.204625-37.732653-6.021168-14.852215-10.436691-38.134065-10.436692-71.852607V333.572717h93.127401V734.582517c2.007056 13.647981 8.028224 18.866327 19.66915 18.866327 17.662093 0 33.718542-15.655037 53.387691-43.352411V333.572717H915.217562v494.538612M587.264602 495.341435c0-52.98628-10.436691-92.324579-29.303018-117.613485-24.887495-33.718542-63.422971-47.767934-102.76127-47.767934-44.155233 0-77.873775 13.647981-102.76127 47.767934-18.866327 24.887495-29.303018 65.028616-29.303019 118.014896v175.81811c0 52.584869 9.232458 88.711878 28.098785 113.599373 24.887495 33.718542 65.028616 51.380635 103.965504 51.380635s79.880831-17.662093 104.768326-51.380635c18.866327-24.887495 27.295962-61.014504 27.295962-113.599373v-176.219521m-93.127401 185.853391c4.816935 48.972168-10.436691 73.05684-39.338299 73.05684-28.901607 0-44.155233-24.084673-39.338298-73.05684v-195.888672c-4.816935-48.972168 10.436691-71.852607 39.338298-71.852606 28.901607 0 44.155233 22.880439 39.338299 71.852606v195.888672zM220.374755 558.764406v269.346923H122.430419v-269.346923S20.873383 228.80439 0 167.388475h102.76127l68.641317 257.705998 68.239906-257.705998h102.76127l-122.029008 391.375931"
                    fill=""
                    p-id="3567"
                  ></path>
                  <path
                    d="M2329.389259 598.102705v-99.951392c0-52.183457-10.436691-90.317523-28.901607-115.205017-24.887495-33.317131-60.211682-50.979224-104.366915-50.979224-45.359467 0-80.683653 17.662093-105.97256 50.979224-18.866327 24.887495-29.70443 65.028616-29.704429 117.212073v171.402587c0 51.782046 12.042336 88.310466 30.908663 112.796551 25.690318 33.317131 61.014504 50.176401 107.176793 50.176401s82.69071-17.662093 107.176794-52.98628c10.838103-15.655037 17.662093-33.317131 20.873383-52.98628 0.802822-8.831047 3.21129-28.901607 3.211289-57.803214v-14.049392h-93.127401c0 35.725598 0 56.598981-0.802822 61.415915-5.218346 23.683261-17.662093 35.725598-39.73971 35.725598-30.507252 0-43.352411-22.880439-42.951-67.838495V598.102705h176.219522m-176.219522-127.648765c0-45.760878 12.443748-58.204626 42.148178-58.204626 29.303018 0 40.943944 13.647981 40.943943 59.007448v53.387691h-83.092121v-54.190513zM1918.74559 330.762838c-32.514308 0-65.028616 20.070561-93.528812 55.394747V172.20541h-87.909056v655.905919h87.909056V778.73775c29.70443 36.52842 61.817327 55.394747 93.528812 55.394747 35.324187 0 61.014504-18.866327 73.05684-55.394747 6.021168-20.873383 9.633869-52.584869 9.633869-97.944336v-195.888671c0-46.162289-6.021168-77.873775-12.042336-97.542924-11.640925-36.127009-35.324187-56.598981-70.648373-56.598981m-10.03528 355.248922c0 48.972168-11.640925 67.838495-36.929832 67.838495-14.450804 0-31.310074-7.626813-46.162289-22.479028v-296.642885c14.852215-14.450804 31.711486-22.479028 46.162289-22.479028 25.690318 0 36.929831 14.450804 36.929832 63.422971v210.339475zM1663.849471 828.111329h-93.127401v-53.789102C1535.397883 814.864759 1505.693454 834.935319 1473.179145 834.935319c-28.500196 0-48.570757-13.647981-58.204625-37.732653-6.021168-14.852215-10.436691-38.134065-10.436692-71.852607V338.791062h93.127401v396.192866c2.007056 13.647981 8.028224 18.866327 19.66915 18.866327 17.662093 0 33.718542-15.655037 53.387691-43.352411V338.791062h93.127401v489.320267"
                    fill="#FFFFFF"
                    p-id="3568"
                  ></path>
                  <path
                    d="M1311.410427 828.111329h-97.944335V265.332811h-102.76127V172.20541h308.28381v93.127401h-107.578205v562.778518"
                    fill="#FFFFFF"
                    p-id="3569"
                  ></path></svg
              ></a>
            </div> -->
          </div>
          <el-container>
            <el-form
              :model="form"
              label-width="80px"
              label-position="left"
              style="width: 100%"
            >
              <el-form-item label="模式设置:" style="display: none">
                <el-radio v-model="advanced" label="1">基础模式</el-radio>
                <el-radio v-model="advanced" label="2">进阶模式</el-radio>
              </el-form-item>
              <el-form-item label="订阅链接:">
                <el-input
                  v-model="form.sourceSubUrl"
                  type="textarea"
                  rows="3"
                  placeholder="支持各种订阅链接或单节点链接，多个链接每行一个或用 | 分隔"
                />
              </el-form-item>
              <el-form-item label="客户端项:">
                <el-select v-model="form.clientType" style="width: 100%">
                  <el-option
                    v-for="(v, k) in options.clientTypes"
                    :key="k"
                    :label="k"
                    :value="v"
                  ></el-option>
                </el-select>
              </el-form-item>
              <el-form-item label="后端地址:">
                <el-select
                  v-model="form.customBackend"
                  allow-create
                  filterable
                  placeholder="可输入自己的后端"
                  style="width: 100%"
                >
                  <el-option
                    v-for="(v, k) in options.customBackend"
                    :key="k"
                    :label="k"
                    :value="v"
                  ></el-option>
                </el-select>
              </el-form-item>
              <el-form-item label="短链选择:">
                <el-select
                  v-model="form.shortType"
                  allow-create
                  filterable
                  placeholder="可输入其他可用短链API"
                  style="width: 100%"
                >
                  <el-option
                    v-for="(v, k) in options.shortTypes"
                    :key="k"
                    :label="k"
                    :value="v"
                  ></el-option>
                </el-select>
              </el-form-item>
              <div v-if="advanced === '2'">
                <el-form-item label="远程配置:">
                  <el-select
                    v-model="form.remoteConfig"
                    allow-create
                    filterable
                    placeholder="请选择"
                    style="width: 100%"
                  >
                    <el-option-group
                      v-for="group in options.remoteConfig"
                      :key="group.label"
                      :label="group.label"
                    >
                      <el-option
                        v-for="item in group.options"
                        :key="item.value"
                        :label="item.label"
                        :value="item.value"
                      ></el-option>
                    </el-option-group>
                    <el-button
                      slot="append"
                      @click="gotoRemoteConfig"
                      icon="el-icon-link"
                      >配置示例</el-button
                    >
                  </el-select>
                </el-form-item>
                <el-form-item label-width="0px">
                  <el-collapse>
                    <el-collapse-item>
                      <template slot="title">
                        <el-form-item label="高级功能:" style="width: 100%">
                          <el-button
                            type="limr"
                            style="width: 100%"
                            icon="el-icon-more-outline"
                            >点击显示/隐藏</el-button
                          >
                        </el-form-item>
                      </template>
                      <el-form-item label="包含节点:">
                        <el-input
                          v-model="form.includeRemarks"
                          placeholder="要保留的节点，支持正则"
                        />
                      </el-form-item>
                      <el-form-item label="排除节点:">
                        <el-input
                          v-model="form.excludeRemarks"
                          placeholder="要排除的节点，支持正则"
                        />
                      </el-form-item>
                      <el-form-item label="节点命名:">
                        <el-input
                          v-model="form.rename"
                          placeholder="原始命名@重命名"
                        />
                      </el-form-item>
                      <el-form-item label="订阅命名:">
                        <el-input
                          v-model="form.filename"
                          placeholder="返回的订阅文件名"
                        />
                      </el-form-item>
                      <el-form-item label-width="0px">
                        <el-row type="flex">
                          <el-col>
                            <el-checkbox
                              v-model="form.nodeList"
                              label="仅输出节点信息"
                              border
                              style="margin-top: 5.9px"
                            ></el-checkbox>
                          </el-col>
                          <el-col>
                            <el-popover
                              placement="bottom"
                              v-model="form.extraset"
                            >
                              <el-row>
                                <el-checkbox
                                  v-model="form.emoji"
                                  label="Emoji"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.new_name"
                                  label="Clash New Field"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.udp"
                                  label="启用 UDP"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.tfo"
                                  label="启用 TFO"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.appendType"
                                  label="节点类型"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.sort"
                                  label="排序节点"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.scv"
                                  label="跳过证书验证"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.fdn"
                                  label="过滤非法节点"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.tpl.surge.doh"
                                  label="Surge.DoH"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.tpl.clash.doh"
                                  label="Clash.DoH"
                                ></el-checkbox>
                              </el-row>
                              <el-row>
                                <el-checkbox
                                  v-model="form.insert"
                                  label="网易云"
                                ></el-checkbox>
                              </el-row>
                              <el-button slot="reference">更多选项</el-button>
                            </el-popover>
                          </el-col>
                        </el-row>
                      </el-form-item>
                    </el-collapse-item>
                  </el-collapse>
                </el-form-item>
              </div>

              <div style="margin-top: 30px"></div>

              <el-divider content-position="center">
                <i class="el-icon-magic-stick"></i>
              </el-divider>

              <el-form-item label="定制订阅:">
                <el-input class="copy-content" disabled v-model="customSubUrl">
                  <el-button
                    slot="append"
                    v-clipboard:copy="customSubUrl"
                    v-clipboard:success="onCopy"
                    ref="copy-btn"
                    icon="el-icon-document-copy"
                    >复制</el-button
                  >
                </el-input>
              </el-form-item>
              <el-form-item label="订阅短链:">
                <el-input
                  class="copy-content"
                  disabled
                  v-model="curtomShortSubUrl"
                >
                  <el-button
                    slot="append"
                    v-clipboard:copy="curtomShortSubUrl"
                    v-clipboard:success="onCopy"
                    ref="copy-btn"
                    icon="el-icon-document-copy"
                    >复制</el-button
                  >
                </el-input>
              </el-form-item>

              <el-form-item
                label-width="0px"
                style="margin-top: 40px; text-align: center"
              >
                <el-button
                  style="width: 120px"
                  type="danger"
                  @click="makeUrl"
                  :disabled="form.sourceSubUrl.length === 0"
                  >生成订阅链接</el-button
                >
                <el-button
                  style="width: 120px"
                  type="danger"
                  @click="makeShortUrl"
                  :loading="loading"
                  :disabled="customSubUrl.length === 0"
                  >生成短链接</el-button
                >
                <!-- <el-button style="width: 120px" type="primary" @click="surgeInstall" icon="el-icon-connection">一键导入Surge</el-button> -->
              </el-form-item>

              <el-form-item label-width="0px" style="text-align: center">
                <el-button
                  style="width: 120px"
                  type="primary"
                  @click="dialogUploadConfigVisible = true"
                  icon="el-icon-upload"
                  :loading="loading"
                  >自定义配置</el-button
                >
                <el-button
                  style="width: 120px"
                  type="primary"
                  @click="clashInstall"
                  icon="el-icon-connection"
                  :disabled="customSubUrl.length === 0"
                  >一键导入Clash</el-button
                >
              <!-- </el-form-item>
              <el-form-item label-width="0px" style="text-align: center">
                <el-button
                  style="width: 250px"
                  type="warning"
                  icon="el-icon-video-play"
                  @click="gotovideo"
                  >视频教程</el-button
                >
              </el-form-item>
              <el-form-item label-width="0px" style="text-align: center">
                <a
                  href="https://cdn.jsdelivr.net/gh/limr95/webcdn@1.3/dyzh.apk"
                  style="text-decoration: none; color: #ffffff"
                >
                  <el-button
                    style="width: 250px"
                    type="success"
                    icon="el-icon-download"
                    >Android客户端</el-button
                  ></a
                > -->
              </el-form-item>
            </el-form>
          </el-container>
        </el-card>
      </el-col>
    </el-row>

    <el-dialog
      :visible.sync="dialogUploadConfigVisible"
      :show-close="false"
      :close-on-click-modal="false"
      :close-on-press-escape="false"
      width="80%"
    >
      <div slot="title">
        Remote config upload
        <el-popover trigger="hover" placement="right" style="margin-left: 10px">
          <el-link
            type="primary"
            :href="sampleConfig"
            target="_blank"
            icon="el-icon-info"
            >参考配置</el-link
          >
          <i class="el-icon-question" slot="reference"></i>
        </el-popover>
      </div>
      <el-form label-position="left">
        <el-form-item prop="uploadConfig">
          <el-input
            v-model="uploadConfig"
            type="textarea"
            :autosize="{ minRows: 15, maxRows: 15 }"
            maxlength="10000"
            show-word-limit
          ></el-input>
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button
          @click="
            uploadConfig = '';
            dialogUploadConfigVisible = false;
          "
          >取 消</el-button
        >
        <el-button
          type="primary"
          @click="confirmUploadConfig"
          :disabled="uploadConfig.length === 0"
          >确 定</el-button
        >
      </div>
    </el-dialog>
  </div>
</template>
<style>
@media (max-width: 460px) {
  .msgbox {
    width: 80%;
  }
}
</style>
<script>
const project = process.env.VUE_APP_PROJECT;
const remoteConfigSample = process.env.VUE_APP_SUBCONVERTER_REMOTE_CONFIG;
const gayhubRelease = process.env.VUE_APP_BACKEND_RELEASE;
const defaultBackend =
  process.env.VUE_APP_SUBCONVERTER_DEFAULT_BACKEND + "/sub?";
const shortUrlBackend = process.env.VUE_APP_MYURLS_DEFAULT_BACKEND + "/short";
const configUploadBackend =
  process.env.VUE_APP_CONFIG_UPLOAD_BACKEND + "/config/upload";
const tgBotLink = process.env.VUE_APP_BOT_LINK;
export default {
  data() {
    return {
      backendVersion: "",
      advanced: "2",

      // 是否为 PC 端
      isPC: true,

      options: {
        clientTypes: {
          Clash: "clash",
          ClashR: "clashr",
          Surge2: "surge&ver=2",
          Surge3: "surge&ver=3",
          Surge4: "surge&ver=4",
          Quantumult: "quan",
          "Quantumult X": "quanx",
          Loon: "loon",
          Mellow: "mellow",
          Surfboard: "surfboard",
          "Shadowsocks(SIP002)": "ss",
          "Shadowsocks Android(SIP008)": "sssub",
          ShadowsocksR: "ssr",
          ShadowsocksD: "ssd",
          V2Ray: "v2ray",
          Trojan: "trojan",
          "混合订阅（mixed）": "mixed",
          自动判断客户端: "auto",
        },
        shortTypes: {
          "suo.yt": "https://suo.yt/short",
          "v1.mk": "https://v1.mk/short",
          "d1.mk": "https://d1.mk/short",
          "dlj.tf": "https://dlj.tf/short",
          "sub.cm": "https://sub.cm/short",
        },
        customBackend: {
          "localhost:25500": "http://localhost:25500/sub?",
          "shaguo.link（自用）": "https://shaguo.link/sub?",
          "subcon.dlj.tf (subconverter作者后端)": "https://subcon.dlj.tf/sub?",
          "api.wcc.best (sub-web作者后端)": "https://api.wcc.best/sub?",
          "api.dler.io（lhie1后端）": "https://api.dler.io/sub?",
          "api.sublink.dev（普拉斯公益后端）": "https://api.sublink.dev/sub?",
          "sub.id9.cc (品云☁️后端)": "https://sub.id9.cc/sub?",
        },
        backendOptions: [
          { value: "http://localhost:25500/sub?" },
          { value: "https://shaguo.link/sub?" },
          { value: "https://subcon.dlj.tf/sub?" },
          { value: "https://api.wcc.best/sub?" },
          { value: "https://api.dler.io/sub?" },
          { value: "https://api.sublink.dev/sub?" },
          { value: "https://sub.id9.cc/sub?" },
        ],
        remoteConfig: [
          {
            label: "Default",
            options: [
              {
                label: "不选，默认",
                value: "",
              },
              {
                label: "My rules",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/Myrules.ini",
              },
              {
                label: "🍟A组去重+重命名",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/%F0%9F%8D%9FA%E7%BB%84.ini",
              },
              {
                label: "🍟B组去重+重命名",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/%F0%9F%8D%9FB%E7%BB%84.ini",
              },
              {
                label: "🍟C组去重+重命名",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/%F0%9F%8D%9FC%E7%BB%84.ini",
              },
              {
                label: "🍟D组去重+重命名",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/%F0%9F%8D%9FD%E7%BB%84.ini",
              },
              {
                label: "🍟E组去重+重命名",
                value:
                  "https://raw.githubusercontent.com/Dashaguo/My-rules/main/%F0%9F%8D%9FE%E7%BB%84.ini",
              },
            ],
          },
          {
            label: "Online rules",
            options: [
              {
                label: "lhie1 rules",
                value:
                  "https://gist.githubusercontent.com/tindy2013/1fa08640a9088ac8652dbd40c5d2715b/raw/lhie1_clash.ini",
              },
              {
                label: "lhie1 rules Full",
                value:
                  "https://gist.githubusercontent.com/tindy2013/1fa08640a9088ac8652dbd40c5d2715b/raw/lhie1_dler.ini",
              },
              {
                label: "ConnersHua rules",
                value:
                  "https://gist.githubusercontent.com/tindy2013/1fa08640a9088ac8652dbd40c5d2715b/raw/connershua_backtocn.ini",
              },
              {
                label: "ACL4SSR_Default",
                value:
                  "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online.ini",
              },
              {
                label: "ACL4SSR_AdblockPlus",
                value:
                  "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_AdblockPlus.ini",
              },
              {
                label: "ACL4SSR_NoAuto",
                value:
                  "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_NoAuto.ini",
              },
              {
                label: "ACL4SSR_Mini",
                value:
                  "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_Mini.ini",
              },
              {
                label: "ACL4SSR_Mini_MultiMode",
                value:
                  "https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/config/ACL4SSR_Online_Mini_MultiMode.ini",
              },
            ],
          },
          {
            label: "universal",
            options: [
              {
                label: "No-Urltest",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/universal/no-urltest.ini",
              },
              {
                label: "Urltest",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/universal/urltest.ini",
              },
            ],
          },
          {
            label: "customized",
            options: [
              {
                label: "Maying",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/customized/maying.ini",
              },
              {
                label: "YoYu",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/customized/yoyu.ini",
              },
              {
                label: "Nexitally",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/customized/nexitally.ini",
              },
            ],
          },
          {
            label: "Special",
            options: [
              {
                label: "NeteaseUnblock(Only rules，No-Urltest)",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/special/netease.ini",
              },
              {
                label: "Basic(仅GEOIP CN + Final)",
                value:
                  "https://subconverter.oss-ap-southeast-1.aliyuncs.com/Rules/RemoteConfig/special/basic.ini",
              },
            ],
          },
        ],
      },
      form: {
        sourceSubUrl: "",
        clientType: "",
        customBackend: "https://shaguo.link/sub?",
        shortType: "https://suo.yt/short",
        remoteConfig:
          "https://raw.githubusercontent.com/Dashaguo/My-rules/main/Myrules.ini",
        excludeRemarks: "",
        includeRemarks: "",
        filename: "",
        rename: "",
        emoji: true,
        nodeList: false,
        extraset: false,
        sort: false,
        udp: true,
        tfo: false,
        scv: false,
        fdn: false,
        appendType: false,
        insert: false, // 是否插入默认订阅的节点，对应配置项 insert_url
        new_name: true, // 是否使用 Clash 新字段

        // tpl 定制功能
        tpl: {
          surge: {
            doh: false, // dns 查询是否使用 DoH
          },
          clash: {
            doh: false,
          },
        },
      },

      loading: false,
      customSubUrl: "",
      curtomShortSubUrl: "",

      dialogUploadConfigVisible: false,
      uploadConfig: "",
      uploadPassword: "",
      myBot: tgBotLink,
      sampleConfig: remoteConfigSample,
    };
  },
  created() {
    document.title = "砂锅的Subconverter";
    this.isPC = this.$getOS().isPc;
  },
  mounted() {
    this.form.clientType = "clash";
    this.getBackendVersion();
  },
  methods: {
    onCopy() {
      this.$message.success("Copied!");
    },
    goToProject() {
      window.open(project);
    },
    gotoTgChannel() {
      window.open(tgBotLink);
    },
    gotoGayhub() {
      window.open(gayhubRelease);
    },
    gotoRemoteConfig() {
      window.open(remoteConfigSample);
    },
    clashInstall() {
      if (this.customSubUrl === "") {
        this.$message.error("请先填写必填项，生成订阅链接");
        return false;
      }

      const url = "clash://install-config?url=";
      window.open(
        url +
          encodeURIComponent(
            this.curtomShortSubUrl !== ""
              ? this.curtomShortSubUrl
              : this.customSubUrl
          )
      );
    },
    surgeInstall() {
      if (this.customSubUrl === "") {
        this.$message.error("请先填写必填项，生成订阅链接");
        return false;
      }

      const url = "surge://install-config?url=";
      window.open(url + this.customSubUrl);
    },
    gotovideo() {
      this.$alert("别忘了关注友善的肥羊哦！", {
        type: "warning",
        confirmButtonText: "确定",
        customClass: "msgbox",
        showClose: false,
      }).then(() => {
        const youtube = "https://www.youtube.com/watch?v=EkZPqsYBTuw";
        window.open(youtube);
      });
    },
    makeUrl() {
      if (this.form.sourceSubUrl === "" || this.form.clientType === "") {
        this.$message.error("订阅链接与客户端为必填项");
        return false;
      }
      //if (
      //  this.form.sourceSubUrl.indexOf("losadhwse") !== -1 &&
      //  this.form.customBackend.indexOf("api.wcc.best") !== -1
      //) {
      //  this.$alert("薯条已将该后端屏蔽，请更换其他后端进行转换！", {
      //    type: "warning",
      //    confirmButtonText: "确定",
      //    customClass: "msgbox",
      //    showClose: false,
      //  });
      //  return false;
      //}

      let backend =
        this.form.customBackend === ""
          ? defaultBackend
          : this.form.customBackend;

      let sourceSub = this.form.sourceSubUrl;
      sourceSub = sourceSub.replace(/(\n|\r|\n\r)/g, "|");

      this.customSubUrl =
        backend +
        "target=" +
        this.form.clientType +
        "&url=" +
        encodeURIComponent(sourceSub) +
        "&insert=" +
        this.form.insert;

      if (this.advanced === "2") {
        if (this.form.remoteConfig !== "") {
          this.customSubUrl +=
            "&config=" + encodeURIComponent(this.form.remoteConfig);
        }
        if (this.form.excludeRemarks !== "") {
          this.customSubUrl +=
            "&exclude=" + encodeURIComponent(this.form.excludeRemarks);
        }
        if (this.form.includeRemarks !== "") {
          this.customSubUrl +=
            "&include=" + encodeURIComponent(this.form.includeRemarks);
        }
        if (this.form.filename !== "") {
          this.customSubUrl +=
            "&filename=" + encodeURIComponent(this.form.filename);
        }
        if (this.form.rename !== "") {
          this.customSubUrl +=
            "&rename=" + encodeURIComponent(this.form.rename);
        }
        if (this.form.appendType) {
          this.customSubUrl +=
            "&append_type=" + this.form.appendType.toString();
        }

        this.customSubUrl +=
          "&emoji=" +
          this.form.emoji.toString() +
          "&list=" +
          this.form.nodeList.toString() +
          "&udp=" +
          this.form.udp.toString() +
          "&tfo=" +
          this.form.tfo.toString() +
          "&scv=" +
          this.form.scv.toString() +
          "&fdn=" +
          this.form.fdn.toString() +
          "&sort=" +
          this.form.sort.toString();

        if (this.form.tpl.surge.doh === true) {
          this.customSubUrl += "&surge.doh=true";
        }

        if (this.form.clientType === "clash") {
          if (this.form.tpl.clash.doh === true) {
            this.customSubUrl += "&clash.doh=true";
          }

          this.customSubUrl += "&new_name=" + this.form.new_name.toString();
        }
      }

      this.$copyText(this.customSubUrl);
      this.$message.success("定制订阅已复制到剪贴板");
    },
    makeShortUrl() {
      if (this.customSubUrl === "") {
        this.$message.warning("请先生成订阅链接，再获取对应短链接");
        return false;
      }

      let duan =
        this.form.shortType === "" ? shortUrlBackend : this.form.shortType;

      this.loading = true;

      let data = new FormData();
      data.append("longUrl", btoa(this.customSubUrl));

      this.$axios
        .post(duan, data, {
          header: {
            "Content-Type": "application/form-data; charset=utf-8",
          },
        })
        .then((res) => {
          if (res.data.Code === 1 && res.data.ShortUrl !== "") {
            this.curtomShortSubUrl = res.data.ShortUrl;
            this.$copyText(res.data.ShortUrl);
            this.$message.success("短链接已复制到剪贴板");
          } else {
            this.$message.error("短链接获取失败：" + res.data.Message);
          }
        })
        .catch(() => {
          this.$message.error("短链接获取失败");
        })
        .finally(() => {
          this.loading = false;
        });
    },
    confirmUploadConfig() {
      if (this.uploadConfig === "") {
        this.$message.warning("远程配置不能为空");
        return false;
      }

      this.loading = true;

      let data = new FormData();
      data.append("password", this.uploadPassword);
      data.append("config", this.uploadConfig);

      this.$axios
        .post(configUploadBackend, data, {
          header: {
            "Content-Type": "application/form-data; charset=utf-8",
          },
        })
        .then((res) => {
          if (res.data.Code === 1 && res.data.url !== "") {
            this.$message.success(
              "远程配置上传成功，配置链接已复制到剪贴板，有效期三个月望知悉"
            );

            // 自动填充至『表单-远程配置』
            this.form.remoteConfig = res.data.Url;
            this.$copyText(this.form.remoteConfig);

            this.dialogUploadConfigVisible = false;
          } else {
            this.$message.error("远程配置上传失败：" + res.data.Message);
          }
        })
        .catch(() => {
          this.$message.error("远程配置上传失败");
        })
        .finally(() => {
          this.loading = false;
        });
    },
    backendSearch(queryString, cb) {
      let backends = this.options.backendOptions;

      let results = queryString
        ? backends.filter(this.createFilter(queryString))
        : backends;

      // 调用 callback 返回建议列表的数据
      cb(results);
    },
    createFilter(queryString) {
      return (candidate) => {
        return (
          candidate.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0
        );
      };
    },
    getBackendVersion() {
      this.$axios
        .get(
          defaultBackend.substring(0, defaultBackend.length - 5) + "/version"
        )
        .then((res) => {
          this.backendVersion = res.data.replace(/backend\n$/gm, "");
          this.backendVersion = this.backendVersion.replace("subconverter", "");
        });
    },
  },
};
</script>
