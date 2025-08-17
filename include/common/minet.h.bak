#pragma once

#include <cstdint>
#include <string>
#include <memory>
#include "proto/packet_head.pb.h"

namespace common {
namespace minet {

class Message; // 前向声明
using MessagePtr = std::shared_ptr<Message>;
using ConstMessagePtr = std::shared_ptr<const Message>;
using ConstMessage = const Message;

class Packet {
private:
    uint16_t cmd_id_;
    proto::PacketHead head_;
    std::string recv_str_;
    MessagePtr proto_ptr_;

public:
    static const uint16_t const_head_magic;
    static const uint16_t const_tail_magic;

private:
    static const uint32_t max_parse_fail_log_len;

public:
    Packet();
    ~Packet();

    int32_t clear();
    uint16_t getCmdId() const;
    uint32_t getBodyLen() const;
    uint32_t getPacketLen() const;
    static uint32_t getPacketLen(const char*, uint32_t);
    int32_t serializeToString(std::string&) const;
    int32_t serializeToArray(char*, uint32_t) const;
    int32_t parseFromString(const std::string&);
    int32_t parseFromArray(const char*, uint32_t);
    int32_t copyHead(const Packet&);
    int32_t copyHead(const proto::PacketHead&);
    int32_t copyHeadAndStr(const Packet&);
    int32_t setCmdIdAndRecvStr(uint32_t, std::string&&);
    int32_t clearHeadForClient();
    int32_t setMessage(uint32_t, ConstMessage&);
    MessagePtr getProto();
    int32_t setMessagePtr(uint32_t, ConstMessagePtr);
    ConstMessagePtr getConstMessage();
    std::string getHeadDebugString() const;
    std::string getProtoDebugString() const;
    static std::string encodeShortStringToBase64(const std::string&);
    uint32_t getHeadLen() const;
    uint32_t getSendOffset();
    uint32_t getThreadOffset();
    void tamperMessage();
    const proto::PacketHead& getHead() const;
    void setHead(const proto::PacketHead&);
    uint32_t getPacketId() const;
    void setPacketId(uint32_t);
    uint32_t getRpcId() const;
    void setRpcId(uint32_t);
    uint64_t getClientSequenceId() const;
    void setClientSequenceId(uint64_t);
    uint32_t getEnetChannelId() const;
    void setEnetChannelId(uint32_t);
    uint32_t getEnetIsReliable() const;
    void setEnetIsReliable(uint32_t);
    uint64_t getSentMs() const;
    void setSentMs(uint64_t);
    uint32_t getUserId() const;
    void setUserId(uint32_t);
    uint32_t getUserIp() const;
    void setUserIp(uint32_t);
    uint32_t getUserSessionId() const;
    void setUserSessionId(uint32_t);
    uint32_t getHomeUserId() const;
    void setHomeUserId(uint32_t);
    uint64_t getRecvTimeMs() const;
    void setRecvTimeMs(uint64_t);
    uint32_t getRpcBeginTimeMs() const;
    void setRpcBeginTimeMs(uint32_t);
    uint32_t getSenderAppId() const;
    void setSenderAppId(uint32_t);
    uint32_t getSenderLoad() const;
    void setSenderLoad(uint32_t);
    std::string getSpanContextStr() const;
    void setSpanContextStr(std::string);
    void setExt(uint32_t, uint32_t);
    uint32_t getExt(uint32_t);
    uint32_t getSourceService() const;
    void setSourceService(uint32_t);
    uint32_t getTargetService() const;
    void setTargetService(uint32_t);
    void setServiceAppId(uint32_t, uint32_t);
    uint32_t getServiceAppId(uint32_t);
    void setSource(uint32_t, uint32_t);
    uint32_t getSourceAppId();
    void setTarget(uint32_t, uint32_t);
    uint32_t getTargetAppId();
    void setGameThreadIndex(uint32_t);
    int32_t getGameThreadIndex();
    void setMultiThreadIndex(uint32_t);
    int32_t getMultiThreadIndex();

private:
    const std::string& getRecvStr() const;
    int32_t doSerializeToArray(char*, uint32_t) const;

public:
    static bool isPacketBegin(const char*, uint32_t);
    static uint32_t getMinPacketLen();


};



} // namespace minet
} // namespace common