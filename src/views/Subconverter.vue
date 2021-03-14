<template>
  <div>
    <el-row style="margin-top: 10px">
      <el-col>
        <el-card>
          <div slot="header">
            Subconverter
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
                              label="输出Node List"
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
                                  label="过滤无用节点"
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
